---
description: '詳細については、次を参照してください: idl_module'
title: idl_module (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 01fbb6cb04f31d9df4466e148a89fccb012835e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183140"
---
# <a name="idl_module"></a>idl_module

.Dll ファイル内のエントリポイントを指定します。

## <a name="syntax"></a>構文

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>パラメーター

*name*<br/>
.Idl ファイルに表示されるコードブロックのユーザー定義名。

*dllname*<br/>
Optionalエクスポートを格納している .dll ファイル。

*uuid*<br/>
Optional一意の ID。

*helpstring*<br/>
Optionalタイプライブラリの説明に使用する文字列。

*helpstringcontext*<br/>
Optional.Hlp または .chm ファイル内のヘルプトピックの ID。

*helpcontext*<br/>
Optionalこのタイプライブラリのヘルプ ID です。

*表示*<br/>
Optionalライブラリが表示されないようにするパラメーター。 詳細については、「 [hidden](/windows/win32/Midl/hidden) 」の MIDL 属性に関する説明を参照してください。

*限定*<br/>
Optionalライブラリのメンバーは、任意に呼び出すことはできません。 詳細については、「 [restricted](/windows/win32/Midl/restricted) 」の MIDL 属性に関する説明を参照してください。

*関数の宣言*<br/>
定義する関数。

## <a name="remarks"></a>解説

**Idl_module** C++ 属性を使用すると、.dll ファイルのエントリポイントを指定できます。これにより、.dll ファイルからインポートできます。

**Idl_module** 属性には、 [module](/windows/win32/Midl/module) MIDL 属性と同様の機能があります。

.Dll ファイルからエクスポートできる COM オブジェクトから任意のものをエクスポートするには、.idl ファイルのライブラリブロックに DLL エントリポイントを配置します。

では、2つの手順で **idl_module** を使用する必要があります。 まず、名前と DLL のペアを定義する必要があります。 次に、 **idl_module** を使用してエントリポイントを指定するときに、名前とその他の属性を指定します。

## <a name="example"></a>例

次のコードは、 **idl_module** 属性の使用方法を示しています。

```cpp
// cpp_attr_ref_idl_module.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];
[idl_module(name="MyLib"), entry(4), usesgetlasterror]
void FuncName(int i);
```

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[キー](entry.md)
