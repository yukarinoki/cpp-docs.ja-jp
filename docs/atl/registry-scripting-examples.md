---
title: レジストリスクリプトの例
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 0e225ce28309aa619fd9436d8f4b93e60544e86c
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168749"
---
# <a name="registry-scripting-examples"></a>レジストリスクリプトの例

このトピックのスクリプト例では、キーをシステムレジストリに追加する方法、レジストラー COM サーバーを登録する方法、および複数の解析ツリーを指定する方法を示します。

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER にキーを追加する

次の解析ツリーは、単一のキーをシステムレジストリに追加する単純なスクリプトを示しています。 特に、スクリプトはキー `MyVeryOwnKey`をに`HKEY_CURRENT_USER`追加します。 また、新しいキーにの既定の`HowGoesIt`文字列値が割り当てられます。

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

これで、スクリプトによってサブ`HasASubkey`キーが`MyVeryOwnKey`に追加されます。 このサブキーに対して`PrettyCool` 、サブキー (既定`DWORD`値は 55) と`ANameValue`名前付きの値 (の`WithANamedValue`文字列値) の両方が追加されます。

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>レジストラー COM サーバーを登録する

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

実行時に、この解析ツリーによっ`ATL.Registrar`てキー `HKEY_CLASSES_ROOT`がに追加されます。 この新しいキーに対して、次のようになります。

- キー `ATL Registrar Class`の既定の文字列値としてを指定します。

- サブ`CLSID`キーとしてを追加します。

- に`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`対し`CLSID`てを指定します。 (この値は、で`CoCreateInstance`使用するレジストラーの CLSID です)。

は`CLSID`共有されているため、登録解除モードでは削除しないでください。 ステートメント`NoRemove CLSID`では、をレジスタモードで開き`CLSID` 、登録解除モードでは無視することを指定することによってこれを行います。

この`ForceRemove`ステートメントは、キーを再作成する前にキーとそのすべてのサブキーを削除することによって、ハウスキーピング機能を提供します。 これは、サブキーの名前が変更された場合に便利です。 このスクリプトの例で`ForceRemove`は、が既`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`に存在するかどうかを確認します。 次のように`ForceRemove`なります。

- とその`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`すべてのサブキーを再帰的に削除します。

- を再作成`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`します。

- の`ATL Registrar Class`既定の文字列値とし`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`てを追加します。

解析ツリーで、に2つの新しい`{44EC053A-400F-11D0-9DCD-00A0C90391D3}`サブキーが追加されました。 最初のキー `ProgID`は、ProgID である既定の文字列値を取得します。 2番目の`InprocServer32`キーは、既定の文字列値`%MODULE%`を取得します。これは、この記事の[置換可能なパラメーター (レジストラーのプリプロセッサ) を使用して](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)、「」セクションで説明されているプリプロセッサの値です。 `InprocServer32`また、は、という`ThreadingModel`文字列値を持つ名前付き`Apartment`の値を取得します。

## <a name="specify-multiple-parse-trees"></a>複数の解析ツリーを指定する

スクリプト内に複数の解析ツリーを指定するには、1つのツリーを別のツリーの最後に配置します。 たとえば、次のスクリプトは、キーを`MyVeryOwnKey`と`HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER`の両方の解析ツリーに追加します。

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
> レジストラースクリプトでは、4K は最大トークンサイズです。 (トークンは、構文内で認識可能な要素です)。`HKCR`前のスクリプトの例`HKEY_CURRENT_USER`では、 `'MyVeryOwnKey'`、、 `'HowGoesIt'` 、およびはすべてトークンです。

## <a name="see-also"></a>関連項目

[Creating Registrar Scripts](../atl/creating-registrar-scripts.md)
