---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "Response Header"
linkTitle: "Response Header"
date: 2017-01-05
description: Here is the header for the response object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Network {
    class Response {
        public:
            Response();
            ~Response();

            void SetStatusCode(int const &);
            void SetStatusMsg(std::string const &);

            std::string getStatusMsg();
            int getStatusCode();
        protected:
        private:
            int statusCode;
            std::string statusMsg;
    };
}
{{< / highlight >}}
