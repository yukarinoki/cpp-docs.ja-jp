---
description: '詳細情報: 解析ツリーについて'
title: ATL レジストラーと解析ツリー
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: cae5256bf932478135db747f80816378e61429a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138243"
---
# <a name="understanding-parse-trees"></a>解析ツリーについて

レジストラースクリプトでは、1つまたは複数の解析ツリーを定義できます。各解析ツリーには次の形式があります。

> \<root key>{\<registry expression>}+

ここで、

> \<root key> :: = HKEY_CLASSES_ROOT \| HKEY_CURRENT_USER \|\
> &emsp;HKEY_LOCAL_MACHINE \| HKEY_USERS \|\
> &emsp;HKEY_PERFORMANCE_DATA \| HKEY_DYN_DATA \|\
> &emsp;HKEY_CURRENT_CONFIG \| HKCR \| HKCU \|\
> &emsp;HKLM \| HKU \| H D \| HKDD \| HKCC

> \<registry expression>::= \<Add Key> \|\<Delete Key>

> \<Add Key>:: = \[ **ForceRemove** \| **noremove** \| **val**] \<Key Name> [ \<Key Value> ] [{ \<Add Key> }]

> \<Delete Key> :: = **削除**\<Key Name>

> \<Key Name> ::= **'**\<AlphaNumeric>+**'**

> \<AlphaNumeric> :: = *NULL 以外の任意の文字、つまり ASCII 0*

> \<Key Value> ::= \<Key Type>\<Key Name>

> \<Key Type> :: = **s** \| **d**

> \<Key Value> ::= **'**\<AlphaNumeric>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT` とは同等であり、と `HKCR` `HKEY_CURRENT_USER` `HKCU` は等価です。

解析ツリーでは、に複数のキーとサブキーを追加でき \<root key> ます。 その場合、サブキーのハンドルは、パーサーがすべてのサブキーの解析を完了するまで開いたままになります。 この方法は、次の例に示すように、一度に1つのキーを操作するよりも効率的です。

```rgs
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

ここでは、最初にレジストラーが開きます (作成し `HKEY_CLASSES_ROOT\MyVeryOwnKey` ます)。 次に、サブキーがあることを確認し `MyVeryOwnKey` ます。 に対してキーを閉じるのではなく `MyVeryOwnKey` 、レジストラーはハンドルを保持し、 `HasASubKey` この親ハンドルを使用してを開きます (作成します)。 (親ハンドルが開いていない場合は、システムレジストリの速度が低下する可能性があります)。このため、を開い `HKEY_CLASSES_ROOT\MyVeryOwnKey` て、 `HasASubKey` を `MyVeryOwnKey` 親として開くと、を開く `MyVeryOwnKey` 、閉じる `MyVeryOwnKey` 、および開くよりも高速です `MyVeryOwnKey\HasASubKey` 。

## <a name="see-also"></a>関連項目

[レジストラースクリプトの作成](../atl/creating-registrar-scripts.md)
