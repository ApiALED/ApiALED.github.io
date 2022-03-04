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
            const std::vector<std::string> Methods = {
                "GET",
                "HEAD",
                "POST",
                "PUT",
                "DELETE",
                "CONNECT",
                "OPTIONS",
                "TRACE",
                "PATCH",
            };
            const std::vector<std::string> Headers = {
                "A-IM",
                "Accept",
                "Accept-Charset",
                "Accept-Encoding",
                "Accept-Language",
                "Accept-Datetime",
                "Access-Control-Request-Method",
                "Access-Control-Request-Headers",
                "Authorization",
                "Cache-Control",
                "Connection",
                "Content-Length",
                "Content-Type",
                "Cookie",
                "Date",
                "Expect",
                "Forwarded",
                "From",
                "Host",
                "If-Match",
                "If-Modified-Since",
                "If-None-Match",
                "If-Range",
                "If-Unmodified-Since",
                "Max-Forwards",
                "Origin",
                "Pragma",
                "Proxy-Authorization",
                "Range",
                "Referer",
                "TE",
                "User-Agent",
                "Upgrade",
                "Via",
                "Warning"
            };
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
