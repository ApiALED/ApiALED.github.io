---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "IModules Header"
linkTitle: "IModules Header"
date: 2017-01-05
description: Here is the header for the IModule object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia {
    class IModules {
        public:
            virtual std::string const &getModuleName() = 0;
            virtual bool runModule() = 0;

            virtual ~IModules() {}

        protected:
        private:
    };
}
{{< / highlight >}}
