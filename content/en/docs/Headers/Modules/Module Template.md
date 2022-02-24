---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "ModuleTemplate Header"
linkTitle: "ModuleTemplate Header"
date: 2017-01-05
description: Here is the header for the Module Template object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia
{
    class moduleTemplate : public IModules
    {
    private:
    public:
        moduleTemplate();
        /*
         * Returns the name of the module.
         */
        const std::string &getModuleName();
        /*
         * Run the module.
         */
        bool runModule();
        ~moduleTemplate();
    };
    /*
     * Returns a shared pointer of the module.
     */
    boost::shared_ptr<IModules> createModule() {
        return boost::make_shared<moduleTemplate>();
    }
}

BOOST_DLL_ALIAS(
    Zia::createModule,
    createModule
)
{{< / highlight >}}
