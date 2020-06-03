---
title: ATL レジストラーと解析ツリー
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: de2cea9b0e7b7c62236f708f9aa8217eaa5df51d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168697"
---
# <a name="understanding-parse-trees"></a>解析ツリーについて

レジストラースクリプトでは、1つまたは複数の解析ツリーを定義できます。各解析ツリーには次の形式があります。

> \<ルートキー> {\<registry expression>} +

ここで、

> \<ルートキー>:: = HKEY_CLASSES_ROOT |HKEY_CURRENT_USER | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_LOCAL_MACHINE |HKEY_USERS | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_PERFORMANCE_DATA |HKEY_DYN_DATA | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_CURRENT_CONFIG |HKCR |HKCU | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKLM |HKU |H/D |HKDD |HKCC

> \<レジストリ式>:: = \<キーの追加> |\<キー> の削除

> \<キーの追加>:: =**[ForceRemove** | **noremove** | **val**]\<キー名>\<[キー値>] [\<{追加キー>}]

> \<キーの削除>:: = キー名の**削除**\<>

> \<キー名>:: = **'**\<英数字>+**'**

> \<英数字>:: = *NULL 以外の任意の文字、つまり ASCII 0*

> \<キー値>:: = \<キーの種類\<>キー名>

> \<キーの種類>:: = **s** | **d**

> \<キー値>:: = **'**\<英数字>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT`と`HKCR`は同等です。`HKEY_CURRENT_USER`と`HKCU`は同等です。などなど。

解析ツリーでは、 \<ルートキー> に複数のキーとサブキーを追加できます。 その場合、サブキーのハンドルは、パーサーがすべてのサブキーの解析を完了するまで開いたままになります。 この方法は、次の例に示すように、一度に1つのキーを操作するよりも効率的です。

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

ここでは、最初にレジストラーが開き`HKEY_CLASSES_ROOT\MyVeryOwnKey`ます (作成します)。 次に、サブ`MyVeryOwnKey`キーがあることを確認します。 に対し`MyVeryOwnKey`てキーを閉じるのではなく、レジストラーはハンドルを保持し`HasASubKey` 、この親ハンドルを使用してを開きます (作成します)。 (親ハンドルが開いていない場合は、システムレジストリの速度が低下する可能性があります)。このため、 `HKEY_CLASSES_ROOT\MyVeryOwnKey`を開いて`HasASubKey` 、 `MyVeryOwnKey`を親として開くと`MyVeryOwnKey`、を`MyVeryOwnKey`開く、閉じる、 `MyVeryOwnKey\HasASubKey`および開くよりも高速です。

## <a name="see-also"></a>関連項目

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
