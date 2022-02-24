---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "Request Header"
linkTitle: "Request Header"
date: 2017-01-05
description: Here is the header for the request object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Network {
    class Request {
        public:
            Request();
            ~Request();
            void setURL(const std::string &);
            void setMethod(const std::string &);
            void setRequest(const std::vector<std::string> &);

            std::string &getURL();
            std::string &getMethod();
            std::vector<std::string> &getRequest();
        protected:
        private:
            std::string URL;
            std::string method;
            std::vector<std::string> request;
    };
}
{{< / highlight >}}
