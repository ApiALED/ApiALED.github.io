---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "ThreadPool Header"
linkTitle: "ThreadPool Header"
date: 2017-01-05
description: Here is the header for the ThreadPool object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia {
    class ThreadPool {
        public:
            ThreadPool();
            ~ThreadPool();
            /*
             * Function used to create the number of workers given in parameters.
             * You cannot create more workers than the "max_workers" number.
             */
            void createWorker(int nbWorker);
            /*
             * Function to push a function in the task list.
             */
            void push(std::function<void()>);
            /*
             * Function to pop the first function in the task list, and returns it.
             */
            std::function<void()> pop();
            /*
             * Function to join all the thread, and clear the task list.
             */
            void stopThreadPool();
            /*
             * Check if the threadPool is running.
             */
            bool isRunning();
        protected:
        private:
            bool doesRun;
            /*
             * The list of all the thread up and running.
             */
            std::vector<std::thread> workers;
            int max_worker;
            std::mutex _mutex;
            std::condition_variable _cond;
            /*
             * The list of the function that need to be runned by the workers.
             */
            std::vector<std::function<void()>> taskList;
            /*
             * The function runned by all the worker.
             * This function pop the taskList it's not empty.
             * Then a worker run the function that has been poped.
             * If the task list is empty, this function put the worker in a waiting state.
             */
            void run_modules();
    };
}
{{< / highlight >}}
