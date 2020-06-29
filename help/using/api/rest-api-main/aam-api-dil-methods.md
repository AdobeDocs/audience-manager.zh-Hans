---
description: 让您通过数据集成库(DIL)有计划地工作的方法。
seo-description: 让您通过数据集成库(DIL)有计划地工作的方法。
seo-title: 数据集成库 API 方法
solution: Audience Manager
title: 数据集成库 API 方法
uuid: 507e7afd-3ae7-44de-98b0-589d699c453b
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 14%

---


# 数据集成库 API 方法 {#data-integration-library-api-methods}

使您能以编程方式使用(...) [!UICONTROL Data Integration Library] 的方[!UICONTROL DIL]法。

>[!IMPORTANT]
>
>数据集成库API已弃用。 此API用于生成DIL，您现在可以在以下位置自下载： [DIL下载](https://github.com/Adobe-Marketing-Cloud/dil/releases)。

<!-- c_data_integr_library_api.xml -->

## DIL的返回版本 {#return-version-dil}

返回 `GET` 从最旧到最新排序的版本列表的方法。

<!-- r_api_return_versions_dil.xml -->

### 请求

`GET https://api.demdex.com/v1/dil/`

### 响应

成功的请求返回响应 `["4.0", "4.1"]` 代码，如下所示。

```
["4.0", "4.1"]
```

## 返回版本的JSON模式 {#return-json-schema-version}

返 `GET` 回版本 [!DNL JSON] 模式的方 [!UICONTROL DIL] 法。 支持使用版 [!UICONTROL LATEST] 本别名获取最新版本 [!UICONTROL DIL]。

<!-- r_api_return_json_schema_for_version.xml -->

### 请求

`GET https://api.demdex.com/v1/dil/`*`<version>`*

### 响应

成功的请求返回响应 `["4.0", "4.1"]` 代码和数据，如下所示。

```
{ 
    "type": "object", 
    "$schema": "https://json-schema.org/draft-03/schema", 
    "required": true, 
    "additionalProperties": false, 
    "properties": { 
        "core": { 
            "id": "core", 
            "required": true, 
            "type": "object", 
            "properties": { 
                "code": { 
                    "type": "boolean", 
                    "required": true, 
                    "id": "code" 
                }, 
                "instanceVariable": { 
                    "type": "string", 
                    "id": "instanceVariable", 
                    "required": false 
                }, 
                "create": { 
                    "type": "object", 
                    "id": "create", 
                    "required": false, 
                    "properties": { 
                        "initConfig": { 
                            "additionalProperties": false, 
                            "type": "object", 
                            "id": "initConfig", 
                            "required": true, 
                            "properties": { 
                                "declaredId": { 
                                    "id": "declaredId", 
                                    "required": false, 
                                    "type": "object", 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "dpid": { 
                                            "id": "dpid", 
                                            "required": true, 
                                            "type": "string" 
                                        }, 
                                        "dpuuid": { 
                                            "id": "dpuuid", 
                                            "required": true, 
                                            "type": "string" 
                                        } 
                                    } 
                                }, 
                                "containerNSID": { 
                                    "type": "number", 
                                    "id": "containerNSID", 
                                    "required": false 
                                }, 
                                "disableDestinationPublishingIframe": { 
                                    "type": "boolean", 
                                    "id": "disableDestinationPublishingIframe", 
                                    "required": false 
                                }, 
                                "enableErrorReporting": { 
                                    "type": "boolean", 
                                    "id": "enableErrorReporting", 
                                    "required": false 
                                }, 
                                "iframeAkamaiHTTPS": { 
                                    "type": "boolean", 
                                    "id": "iframeAkamaiHTTPS", 
                                    "required": false 
                                }, 
                                "iframeAttachmentDelay": { 
                                    "type": "number", 
                                    "id": "iframeAttachmentDelay", 
                                    "required": false 
                                }, 
                                "mappings": { 
                                    "type": "object", 
                                    "id": "mappings", 
                                    "required": false, 
                                    "additionalProperties": { 
                                        "type": "string" 
                                    } 
                                }, 
                                "removeFinishedScriptsAndCallbacks": { 
                                    "type": "boolean", 
                                    "id": "removeFinishedScriptsAndCallbacks", 
                                    "required": false 
                                }, 
                                "uuidCookie": { 
                                    "type": "object", 
                                    "id": "uuidCookie", 
                                    "additionalProperties": false, 
                                    "required": false, 
                                    "properties": { 
                                        "days": { 
                                            "type": "number", 
                                            "id": "days", 
                                            "required": false 
                                        }, 
                                        "domain": { 
                                            "type": "string", 
                                            "id": "domain", 
                                            "required": false 
                                        }, 
                                        "name": { 
                                            "type": "string", 
                                            "id": "name", 
                                            "required": true 
                                        }, 
                                        "path": { 
                                            "type": "string", 
                                            "id": "path", 
                                            "required": false 
                                        }, 
                                        "secure": { 
                                            "type": "boolean", 
                                            "id": "secure", 
                                            "required": false 
                                        } 
                                    } 
                                }, 
                                "visitorService": { 
                                    "type": "object", 
                                    "id": "visitorService", 
                                    "required": false, 
                                    "properties": { 
                                        "namespace": { 
                                            "type": "string", 
                                            "id": "namespace", 
                                            "required": true 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                } 
            } 
        }, 
        "options": { 
            "id": "options", 
            "type": "object", 
            "required": false, 
            "properties": { 
                "minify": { 
                    "id": "minify", 
                    "required": false, 
                    "type": "boolean" 
                } 
            } 
        }, 
        "include": { 
            "type": "object", 
            "id": "include", 
            "required": false, 
            "properties": { 
                "modules": { 
                    "type": "object", 
                    "id": "modules", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "GoogleAnalytics": { 
                            "type": "object", 
                            "id": "GoogleAnalytics", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "Peer39": { 
                            "type": "object", 
                            "id": "Peer39", 
                            "required": false, 
                            "properties": { 
                                "code": { 
                                    "id": "code", 
                                    "type": "boolean", 
                                    "required": true 
                                } 
                            } 
                        }, 
                        "SiteCatalyst": { 
                            "type": "object", 
                            "id": "SiteCatalyst", 
                            "required": false, 
                            "additionalProperties": false, 
                            "properties": { 
                                "code": { 
                                    "type": "boolean", 
                                    "id": "code", 
                                    "required": true 
                                }, 
                                "init": { 
                                    "type": "object", 
                                    "id": "init", 
                                    "required": false, 
                                    "additionalProperties": false, 
                                    "properties": { 
                                        "siteCatalystInstance": { 
                                            "type": "string", 
                                            "id": "siteCatalystInstance", 
                                            "required": true 
                                        }, 
                                        "dilInstance": { 
                                            "type": "string", 
                                            "id": "dilInstance", 
                                            "required": true 
                                        }, 
                                        "trackedVariables": { 
                                            "id": "trackedVariables", 
                                            "required": false, 
                                            "type": "object", 
                                            "properties": { 
                                                "iteratedNames": { 
                                                    "type": "array", 
                                                    "id": "iteratedNames", 
                                                    "required": false, 
                                                    "items": { 
                                                        "type": "object", 
                                                        "id": "0", 
                                                        "required": true, 
                                                        "properties": { 
                                                            "maxIndex": { 
                                                                "type": "number", 
                                                                "id": "maxIndex", 
                                                                "required": true 
                                                            }, 
                                                            "name": { 
                                                                "type": "string", 
                                                                "id": "name", 
                                                                "required": true 
                                                            } 
                                                        } 
                                                    } 
                                                }, 
                                                "names": { 
                                                    "type": "array", 
                                                    "additionalItems": false, 
                                                    "id": "names", 
                                                    "required": false, 
                                                    "items": [ 
                                                        { 
                                                            "type": "string", 
                                                            "required": true 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        }, 
                                                        { 
                                                            "type": "string", 
                                                            "required": false 
                                                        } 
                                                    ] 
                                                } 
                                            } 
                                        } 
                                    } 
                                } 
                            } 
                        } 
                    } 
                }, 
                "tools": { 
                    "type": "object", 
                    "id": "tools", 
                    "required": false, 
                    "additionalProperties": false, 
                    "properties": { 
                        "getMetaTags": { 
                            "type": "boolean", 
                            "id": "getMetaTags", 
                            "required": false 
                        }, 
                        "getSearchReferrer": { 
                            "type": "boolean", 
                            "id": "getSearchReferrer", 
                            "required": false 
                        }, 
                        "decomposeURI": { 
                            "type": "boolean", 
                            "id": "decomposeURI", 
                            "required": false 
                        } 
                    } 
                } 
            } 
        } 
    } 
} 
```

## 生成DIL {#generate-dil}

一种 `GET` 基于使用 [!UICONTROL DIL] 指定版本的传入请求主体生成的方法 [!UICONTROL DIL]。 如果别名 `LATEST` 用于URL中的版本，则会生成最新版本 [!UICONTROL DIL] 的别名。

<!-- r_api_generate_dil.xml -->

### 请求

`POST https://api.demdex.com/v1/dil/`*`<version>`*`/generate`

### 示例请求

```
{ 
    core: { 
        code: true, 
        instanceVariable: 'dil_instance', 
        create: { 
            initConfig: { 
                declaredId: { 
                    dpid: '159', 
                    dpuuid: '456' 
                }, 
                containerNSID: 81, 
                disableDestinationPublishingIframe: false, 
                enableErrorReporting: false, 
                iframeAkamaiHTTPS: false, 
                iframeAttachmentDelay: 575, 
                mappings: { 
                    c_k1: 'd_k1', 
                    c_k2: 'd_k2' 
                }, 
                removeFinishedScriptsAndCallbacks: false, 
                uuidCookie: { 
                    days: 12, 
                    domain: 'adobe.com', 
                    name: 'adobe_did', 
                    path: '/', 
                    secure: false 
                }, 
                visitorService: { 
                    namespace: 'demofirst' 
                } 
            } 
        } 
    }, 
    options: { 
        minify: true 
    }, 
    include: { 
        modules: { 
            GoogleAnalytics: { 
                code: true 
            }, 
            Peer39: { 
                code: true 
            }, 
            SiteCatalyst: { 
                code: true, 
                init: { 
                    siteCatalystInstance: 'sc_instance', 
                    dilInstance: 'dil_instance', 
                    trackedVariables: { 
                        iteratedNames: [{ 
                            name: 'prop', 
                            maxIndex: 5 
                        }, { 
                            name: 'pev', 
                            maxIndex: 3 
                        }], 
                        names: ['pageName', 'channel', 'campaign', 'products', 'events', 'spe', 'spev1', 'spev2', 'spev3'] 
                    } 
                } 
            } 
        }, 
        tools: { 
            getMetaTags: true, 
            getSearchReferrer: true, 
            decomposeURI: true 
        } 
    } 
} 
```

### 响应

成功的更新会返回响应 `201 created` 代码以及 [!UICONTROL DIL] 代码 [!DNL JavaScript] 。
