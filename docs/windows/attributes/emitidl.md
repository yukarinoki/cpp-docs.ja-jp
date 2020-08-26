---
title: emitidl (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.emitidl
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
ms.openlocfilehash: 32362f287320e69d1680cbe07ca050143b507514
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846330"
---
# <a name="emitidl"></a>emitidl

それ以降のすべての IDL 属性を処理し、生成された .idl ファイルに配置するかどうかを指定します。

## <a name="syntax"></a>構文

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>パラメーター

*状態*<br/>
有効な値の1つは、、、 **`true`** **`false`** 、、 `forced` `restricted` `push` 、または `pop` です。

- **`true`** の場合、ソースコードファイルで検出された idl カテゴリ属性は、生成された .idl ファイルに配置されます。 これは **emitidl**の既定の設定です。

- **`false`** の場合、ソースコードファイルで検出された idl カテゴリ属性は、生成された .idl ファイルには配置されません。

- `restricted`の場合、[モジュール](module-cpp.md)属性なしで IDL 属性をファイル内に配置できます。 コンパイラは .idl ファイルを生成しません。

- の場合、後続の属性をオーバーライドします `forced` 。これにより、ファイル `restricted` に IDL 属性がある場合、ファイルに属性を設定する必要があり `module` ます。

- `push`では、現在の**emitidl**の設定を内部**emitidl**スタックに保存し、 `pop` 内部の**emitidl**スタックの一番上にある任意の値に**emitidl**を設定することができます。

`defaultimports=`*ブール値* \(optional

- *ブール値*がの場合、生成された **`true`** .idl ファイルに docobj .idl がインポートされます。 また、ソースコード内の .h ファイルと同じ名前の .idl ファイル `#include` が .h ファイルと同じディレクトリに存在する場合、生成された .idl ファイルには、その .idl ファイルの import ステートメントが含まれています。

- *Boolean*がの場合、生成された **`false`** .idl ファイルにはインポートされません。 [インポート](import.md)を使用して .idl ファイルを明示的にインポートする必要があります。

## <a name="remarks"></a>解説

ソースコードファイルで **emitidl** C++ 属性が検出されると、生成された .idl ファイルに idl カテゴリ属性が配置されます。 **Emitidl**属性がない場合、ソースコードファイル内の idl 属性は、生成された .idl ファイルに出力されます。

ソースコードファイルには、複数の **emitidl** 属性を含めることができます。 `[emitidl(false)];`後続のがないファイルでが発生した場合 `[emitidl(true)];` 、生成された .idl ファイルには属性は処理されません。

コンパイラが新しいファイルを検出するたびに、 **emitidl** が暗黙的にに設定され **`true`** ます。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)
