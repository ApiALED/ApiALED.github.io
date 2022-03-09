---
categories: ["Headers"]
tags: ["test", "sample", "docs"]
title: "Cofig Header"
linkTitle: "Config Header"
date: 2017-01-05
description: Here is the header for the Config object.
---

{{< highlight cpp "linenos=table, linenostart=1" >}}
namespace Zia {
    class Config {
        public:
            Config();
            ~Config();

            bool LoadConfig(const std::string &);
            std::string const &getPassword();
            std::string const &getModulePath();
            std::list<std::string> const &getModuleList();
            std::string const &getCertPath();
            std::string const &getKeyPath();
            unsigned int &getPort();
        protected:
        private:
            std::list<std::string> ModuleList;
            std::string ModulePath;
            unsigned int port;
            std::string certif_path;
            std::string password;
            std::string key_path;
            bool isDir(const std::string &in_name);
            bool readJsonFile(const std::string &path, const std::string &dir_path);
            bool loadDefaultConfig();
    };
}
{{< / highlight >}}
