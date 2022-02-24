---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "fatalException Header"
linkTitle: "fatalException Header"
date: 2017-01-05
description: Here is the header for the FatalException object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia
{
    class fatalException : public std::exception
    {
        private:
            std::string msg; // The message of the error
            std::string function; // The function where the error occured
        public:
            fatalException(const std::string &msg, const std::string &func); // The constructor of the error. It takes has parameters a message, and the name of the function.
            /* Here is how you should throw this error :  
            * throw(Zia::fatalException(YOUR_MESSAGE, YOUR FUNCTION));
            */
            const char *what() const throw(); // Returns the error message
            const char *getErrorFunction() const throw(); // Returns the name of the function given in the constructor
            ~fatalException() throw();
    };
    
}
{{< / highlight >}}
