---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "Logger Header"
linkTitle: "Logger Header"
date: 2017-01-05
description: Here is the header for the Logger object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia {
    // The enumeration for all the message types
    enum LoggerType {
        Trace,
        Debug,
        Info,
        Warning,
        Error,
        Fatal
    };
    class Logger {
        public:
            Logger();
            ~Logger();

            static void Log(LoggerType type, std::string const &msg); // The function to log something. It takes as parameters a Zia::LoggerType, and the log message
        protected:
        private:
    };
}
{{< / highlight >}}
