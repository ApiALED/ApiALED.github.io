---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "ModuleLoader Header"
linkTitle: "ModuleLoader Header"
date: 2017-01-05
description: Here is the header for the Module Loader object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia {
    class ModuleLoader {
        public:
            ModuleLoader();
            /*
             * Used to load a module. The "name" parameter is the name where the module will be stored in the map 
             */
            boost::function<boost::shared_ptr<IModules>()> load(std::string const &path, const std::string &name);
            /*
             * Function used to unload the module.
             */
            void unload(std::string const &name);
            /*
             * Return a function to call the IModules members.
             */
            boost::function<boost::shared_ptr<IModules>()> getModule(std::string const &name);
            /*
             * Check if the module if loaded.
             */
            bool isLoaded(std::string const &name);
            ~ModuleLoader();

        protected:
        private:
            /*
             * The map of all the modules. 
             */
            std::map<std::string, boost::dll::shared_library> moduleList;
    };
}
{{< / highlight >}}
