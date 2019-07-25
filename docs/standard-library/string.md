---
title: '&lt;string&gt;'
ms.date: 11/04/2016
f1_keywords:
- string/std::<string>
- <string>
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: fda00cd5a8f8768688c8e10f25a0d1f2370a256f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459198"
---
# <a name="ltstringgt"></a>&lt;string&gt;

コンテナーのテンプレート クラス `basic_string` とさまざまなサポート用テンプレートを定義します。

`basic_string` の詳細については、「[basic_string クラス](../standard-library/basic-string-class.md)」を参照してください。

## <a name="syntax"></a>構文

```cpp
#include <string>
```

## <a name="remarks"></a>Remarks

C++ 言語および C++ 標準ライブラリでは、2 種類の文字列がサポートされます。

- よく C 文字列と呼ばれる、null で終わる文字の配列。

- Char のようなすべての`basic_string`テンプレート引数を処理する、型のテンプレートクラスオブジェクト。

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[string](../standard-library/string-typedefs.md#string)|Char 型の要素をとして特殊化し`basic_string`たテンプレートクラスを記述する型。  `string`|
|[wstring](../standard-library/string-typedefs.md#wstring)|Wchar_t 型の要素をとして特殊化し`basic_string`たテンプレートクラスを記述する型。  `wstring`|
|[u16string](../standard-library/string-typedefs.md#u16string)|`basic_string` 型の要素に基づいて特殊化したテンプレート クラス `char16_t` を記述する型。|
|[u32string](../standard-library/string-typedefs.md#u32string)|`basic_string` 型の要素に基づいて特殊化したテンプレート クラス `char32_t` を記述する型。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator+](../standard-library/string-operators.md#op_add)|2 つの文字列オブジェクトを連結します。|
|[operator!=](../standard-library/string-operators.md#op_neq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しくないかどうかを調べます。|
|[operator==](../standard-library/string-operators.md#op_eq_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトと等しいかどうかを調べます。|
|[operator<](../standard-library/string-operators.md#op_lt)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより小さいかどうかを調べます。|
|[operator<=](../standard-library/string-operators.md#op_lt_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以下かどうかを調べます。|
|[operator<\<](../standard-library/string-operators.md#op_lt_lt)|出力ストリームに文字列を挿入するテンプレート関数。|
|[operator>](../standard-library/string-operators.md#op_gt)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|演算子の左辺の文字列オブジェクトが右辺の文字列オブジェクト以上かどうかを調べます。|
|[operator>>](../standard-library/string-operators.md#op_gt_gt)|入力ストリームから文字列を抽出するテンプレート関数。|

### <a name="specialized-template-functions"></a>特殊テンプレート関数

|||
|-|-|
|[hash]()||
|[swap](../standard-library/string-functions.md#swap)|2 つの文字列の、文字の配列を交換します。|
|[stod](../standard-library/string-functions.md#stod)|文字シーケンスを**倍精度浮動小数点**型に変換します。|
|[stof](../standard-library/string-functions.md#stof)|文字シーケンスを**float**に変換します。|
|[stoi](../standard-library/string-functions.md#stoi)|文字シーケンスを integer に変換します。|
|[stold](../standard-library/string-functions.md#stold)|文字シーケンスを**long double**に変換します。|
|[stoll](../standard-library/string-functions.md#stoll)|文字シーケンスを**long 型**に変換します。|
|[stoul](../standard-library/string-functions.md#stoul)|文字シーケンスを**unsigned long**に変換します。|
|[stoull](../standard-library/string-functions.md#stoull)|文字シーケンスを**unsigned long long 型**に変換します。|
|[to_string](../standard-library/string-functions.md#to_string)|値を `string` に変換します。|
|[to_wstring](../standard-library/string-functions.md#to_wstring)|値をワイド `string` に変換します。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[getline テンプレート](../standard-library/string-functions.md#getline)|入力ストリームから文字列を行単位で抽出します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_string クラス](../standard-library/basic-string-class.md)|文字に類する任意のオブジェクトのシーケンスを格納できるオブジェクトを記述するテンプレート クラス。|
|[char_traits 構造体](../standard-library/char-traits-struct.md)|CharType 型の文字に関連付けられている属性を記述するテンプレート クラス。|

### <a name="specializations"></a>特殊化

|||
|-|-|
|[char_traits\<char> 構造体](../standard-library/char-traits-char-struct.md)|テンプレート構造体 `char_traits`\<CharType> を `char` 型の要素に特殊化した構造体。|
|[char_traits<wchar_t> 構造体](../standard-library/char-traits-wchar-t-struct.md)|テンプレート構造体 `char_traits`\<CharType> を `wchar_t` 型の要素に特殊化した構造体。|
|[char_traits<char16_t> 構造体](../standard-library/char-traits-char16-t-struct.md)|テンプレート構造体 `char_traits`\<CharType> を `char16_t` 型の要素に特殊化した構造体。|
|[char_traits<char32_t> 構造体](../standard-library/char-traits-char32-t-struct.md)|テンプレート構造体 `char_traits`\<CharType> を `char32_t` 型の要素に特殊化した構造体。|

## <a name="requirements"></a>必要条件

- **ヘッダー:** \<string>

- **名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
