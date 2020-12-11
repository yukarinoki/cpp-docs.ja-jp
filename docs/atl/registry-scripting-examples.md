---
description: 詳細については、「レジストリスクリプトの例」を参照してください。
title: レジストリスクリプトの例
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 716aa69ed95c784079e72f9b785fedd8c07b0563
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157543"
---
# <a name="registry-scripting-examples"></a>レジストリスクリプトの例

このトピックのスクリプト例では、キーをシステムレジストリに追加する方法、レジストラー COM サーバーを登録する方法、および複数の解析ツリーを指定する方法を示します。

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER にキーを追加する

次の解析ツリーは、単一のキーをシステムレジストリに追加する単純なスクリプトを示しています。 特に、スクリプトはキーをに追加し `MyVeryOwnKey` `HKEY_CURRENT_USER` ます。 また、新しいキーにの既定の文字列値が割り当てられ `HowGoesIt` ます。

```rgs
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

このスクリプトは、次のように複数のサブキーを定義するように簡単に拡張できます。

```rgs
HKCU
{
    'MyVeryOwnKey' = s 'HowGoesIt'
    {
        'HasASubkey'
        {
            'PrettyCool' = d '55'
            val 'ANameValue' = s 'WithANamedValue'
        }
    }
}
```

これで、スクリプトによってサブキーがに追加され `HasASubkey` `MyVeryOwnKey` ます。 このサブキーに対して、 `PrettyCool` サブキー (既定値は `DWORD` 55) と `ANameValue` 名前付きの値 (の文字列値) の両方が追加され `WithANamedValue` ます。

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a> レジストラー COM サーバーを登録する

次のスクリプトは、レジストラー COM サーバー自体を登録します。

```rgs
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
        {
            ProgID = s 'ATL.Registrar'
            InprocServer32 = s '%MODULE%'
            {
                val ThreadingModel = s 'Apartment'
            }
        }
    }
}
```

実行時に、この解析ツリーによってキーがに追加さ `ATL.Registrar` `HKEY_CLASSES_ROOT` れます。 この新しいキーに対して、次のようになります。

- `ATL Registrar Class`キーの既定の文字列値としてを指定します。

- `CLSID`サブキーとしてを追加します。

- `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`に対してを指定し `CLSID` ます。 (この値は、で使用するレジストラーの CLSID です `CoCreateInstance` )。

`CLSID`は共有されているため、登録解除モードでは削除しないでください。 ステートメントでは、を `NoRemove CLSID` `CLSID` レジスタモードで開き、登録解除モードでは無視することを指定することによってこれを行います。

このステートメントは、キーを `ForceRemove` 再作成する前にキーとそのすべてのサブキーを削除することによって、ハウスキーピング機能を提供します。 これは、サブキーの名前が変更された場合に便利です。 このスクリプトの例で `ForceRemove` は、が既に存在するかどうかを確認し `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ます。 次のようになり `ForceRemove` ます。

- `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`とそのすべてのサブキーを再帰的に削除します。

- を再作成 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` します。

- `ATL Registrar Class`の既定の文字列値としてを追加し `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ます。

解析ツリーで、に2つの新しいサブキーが追加されました `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` 。 最初のキーは、 `ProgID` ProgID である既定の文字列値を取得します。 2番目のキーは、 `InprocServer32` 既定の文字列値を取得し `%MODULE%` ます。これは、この記事の [置換可能なパラメーター (レジストラーのプリプロセッサ) を使用して](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)、「」セクションで説明されているプリプロセッサの値です。 `InprocServer32` また、は、という文字列値を持つ名前付きの値を取得し `ThreadingModel` `Apartment` ます。

## <a name="specify-multiple-parse-trees"></a>複数の解析ツリーを指定する

スクリプト内に複数の解析ツリーを指定するには、1つのツリーを別のツリーの最後に配置します。 たとえば、次のスクリプトは、キーを `MyVeryOwnKey` との両方の解析ツリーに追加 `HKEY_CLASSES_ROOT` し `HKEY_CURRENT_USER` ます。

```rgs
HKCR
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

> [!NOTE]
> レジストラースクリプトでは、4K は最大トークンサイズです。 (トークンは、構文内で認識可能な要素です)。前のスクリプトの例では、、、 `HKCR` `HKEY_CURRENT_USER` `'MyVeryOwnKey'` 、および `'HowGoesIt'` はすべてトークンです。

## <a name="see-also"></a>関連項目

[レジストラースクリプトの作成](../atl/creating-registrar-scripts.md)
