---
title: レジストリ スクリプトの例
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 7bcdb7076982e2f0bd08f4fd82bb45f21e61ef20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329336"
---
# <a name="registry-scripting-examples"></a>レジストリ スクリプトの例

このトピックのスクリプト例では、システム レジストリにキーを追加し、レジストラー COM サーバーを登録し、複数の解析ツリーを指定する方法を示します。

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USERにキーを追加する

次の解析ツリーは、システム レジストリに 1 つのキーを追加する単純なスクリプトを示しています。 特に、スクリプトは キー を`MyVeryOwnKey`に`HKEY_CURRENT_USER`追加します。 また、新しいキーにデフォルトの`HowGoesIt`文字列値を割り当てます。

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

このスクリプトは、次のように複数のサブキーを定義するために簡単に拡張できます。

```
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

ここで、スクリプトは サブキー を`HasASubkey`に`MyVeryOwnKey`追加します。 このサブ`PrettyCool`キーには、サブキー (既定値`DWORD`55) と`ANameValue`名前付きの値 (文字列値が 含まれます)`WithANamedValue`の両方が追加されます。

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>レジストラー COM サーバーを登録します。

次のスクリプトは、レジストラー COM サーバー自体を登録します。

```
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

実行時に、この解析ツリーは キー`ATL.Registrar`を`HKEY_CLASSES_ROOT`に追加します。 この新しいキーに対しては、次の手順を実行します。

- キー`ATL Registrar Class`の既定の文字列値として指定します。

- サブ`CLSID`キーとして追加します。

- に`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`指定`CLSID`します。 (この値は、レジストラーの CLSID で使用`CoCreateInstance`します。

共有`CLSID`されているため、登録解除モードでは削除しないでください。 ステートメントは、`NoRemove CLSID`登録モードで開き、`CLSID`登録解除モードで無視する必要があることを示すことによってこれを行います。

この`ForceRemove`ステートメントは、キーを再作成する前に、キーとそのすべてのサブキーを削除することによって、ハウスキーピング機能を提供します。 これは、サブキーの名前が変更された場合に役立ちます。 このスクリプト例では、`ForceRemove`既に存在するかどうかを`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`確認します。 もしそうなら、 `ForceRemove`

- 再帰的に`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`、そのサブキーとそのすべてのサブキーを削除します。

- を再作成`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`します。

- の`ATL Registrar Class`既定の文字列値として追加`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`します。

解析ツリーでは、2 つの新しいサブ`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`キーが に追加されます。 最初のキーは`ProgID`、ProgID の既定の文字列値を取得します。 2 番目の`InprocServer32`キーは、`%MODULE%`既定の文字列値を取得します。 [Using Replaceable Parameters (The Registrar's Preprocessor)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) `InprocServer32`また、名前付きの`ThreadingModel`値を取得します`Apartment`。

## <a name="specify-multiple-parse-trees"></a>複数の解析ツリーを指定する

スクリプト内で複数の解析ツリーを指定するには、1 つのツリーを別のツリーの末尾に配置します。 たとえば、次のスクリプトは、`MyVeryOwnKey`両方`HKEY_CLASSES_ROOT`のパスの解析ツリーにキー 、`HKEY_CURRENT_USER`を追加します。

```
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
> レジストラー スクリプトでは、4K はトークンの最大サイズです。 (トークンは構文内の認識可能な要素です。前のスクリプト例では`HKCR`、 、 `HKEY_CURRENT_USER` `'MyVeryOwnKey'`、、、およびは、`'HowGoesIt'`すべてトークンです。

## <a name="see-also"></a>関連項目

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
