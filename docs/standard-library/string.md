---
description: '詳細情報: &lt; 文字列&gt;'
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: d8b89bf1a9621e863f6608e46557d374cd8e6245
ms.sourcegitcommit: a89eac9acdbd54a181e3bd5d5bc71a3ef3c1abca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "106506118"
---
# `<string>`

コンテナークラステンプレート `basic_string` とさまざまなサポートテンプレートを定義します。

の詳細について `basic_string` は、「 [ `basic_string` クラス](../standard-library/basic-string-class.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
#include <string>
```

## <a name="remarks"></a>Remarks

C++ 言語および C++ 標準ライブラリでは、2 種類の文字列がサポートされます。

- よく C 文字列と呼ばれる、null で終わる文字の配列。

- `basic_string`すべての like テンプレート引数を処理する型のクラステンプレートオブジェクト **`char`** 。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[`string`](../standard-library/string-typedefs.md#string)|`basic_string`型の要素をとして持つクラステンプレートの特殊化を記述する型 **`char`** `string` 。|
|[`wstring`](../standard-library/string-typedefs.md#wstring)|`basic_string`型の要素をとして持つクラステンプレートの特殊化を記述する型 **`wchar_t`** `wstring` 。|
|[`u16string`](../standard-library/string-typedefs.md#u16string)|`basic_string`型の要素に基づいたクラステンプレートの特殊化を記述する型 **`char16_t`** 。|
|[`u32string`](../standard-library/string-typedefs.md#u32string)|`basic_string`型の要素に基づいたクラステンプレートの特殊化を記述する型 **`char32_t`** 。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[`operator+`](../standard-library/string-operators.md#op_add)|2 つの文字列オブジェクトを連結します。|
|[`operator!=`](../standard-library/string-operators.md#op_neq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しくないかどうかを調べます。|
|[`operator==`](../standard-library/string-operators.md#op_eq_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しいかどうかを調べます。|
|[`operator<`](../standard-library/string-operators.md#op_lt)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより小さいかどうかを調べます。|
|[`operator<=`](../standard-library/string-operators.md#op_lt_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以下かどうかを調べます。|
|[`operator<<`](../standard-library/string-operators.md#op_lt_lt)|出力ストリームに文字列を挿入するテンプレート関数。|
|[`operator>`](../standard-library/string-operators.md#op_gt)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより大きいかどうかを調べます。|
|[`operator>=`](../standard-library/string-operators.md#op_gt_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以上かどうかを調べます。|
|[`operator>>`](../standard-library/string-operators.md#op_gt_gt)|入力ストリームから文字列を抽出するテンプレート関数。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|名前|説明|
|-|-|
|`hash`|文字列のハッシュを生成します。|
|[`swap`](../standard-library/string-functions.md#swap)|2 つの文字列の、文字の配列を交換します。|
|[`stod`](../standard-library/string-functions.md#stod)|文字シーケンスをに変換 **`double`** します。|
|[`stof`](../standard-library/string-functions.md#stof)|文字シーケンスをに変換 **`float`** します。|
|[`stoi`](../standard-library/string-functions.md#stoi)|文字シーケンスをに変換 **`int`** します。|
|[`stold`](../standard-library/string-functions.md#stold)|文字シーケンスをに変換 **`long double`** します。|
|[`stoll`](../standard-library/string-functions.md#stoll)|文字シーケンスをに変換 **`long long`** します。|
|[`stoul`](../standard-library/string-functions.md#stoul)|文字シーケンスをに変換 **`unsigned long`** します。|
|[`stoull`](../standard-library/string-functions.md#stoull)|文字シーケンスをに変換 **`unsigned long long`** します。|
|[`to_string`](../standard-library/string-functions.md#to_string)|値を `string` に変換します。|
|[`to_wstring`](../standard-library/string-functions.md#to_wstring)|値をワイド文字列に変換します。|

### <a name="functions"></a>関数

|機能|説明|
|-|-|
|[`getline` テンプレート](../standard-library/string-functions.md#getline)|入力ストリームから行を1行ずつ抽出 `string` します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[`basic_string` 講義](../standard-library/basic-string-class.md)|任意の文字に似たオブジェクトのシーケンスを格納できるオブジェクトを記述するクラステンプレート。|
|[`char_traits` 体型](../standard-library/char-traits-struct.md)|型の文字に関連付けられている属性を記述するクラステンプレート `CharType`|

### <a name="specializations"></a>特殊化

|名前|説明|
|-|-|
|[`char_traits<char>` 体型](../standard-library/char-traits-char-struct.md)|テンプレート構造体を `char_traits<CharType>` 型の要素に特殊化した構造体 **`char`** 。|
|[`char_traits<wchar_t>` 体型](../standard-library/char-traits-wchar-t-struct.md)|テンプレート構造体を `char_traits<CharType>` 型の要素に特殊化した構造体 **`wchar_t`** 。|
|[`char_traits<char16_t>` 体型](../standard-library/char-traits-char16-t-struct.md)|テンプレート構造体を `char_traits<CharType>` 型の要素に特殊化した構造体 **`char16_t`** 。|
|[`char_traits<char32_t>` 体型](../standard-library/char-traits-char32-t-struct.md)|テンプレート構造体を `char_traits<CharType>` 型の要素に特殊化した構造体 **`char32_t`** 。|

## <a name="requirements"></a>必要条件

- **ヘッダー:**`<string>`

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
