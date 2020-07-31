---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 13b6f5c63b9426fc4c31527f0d1ae8291d07807f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222213"
---
# <a name="ltstring_viewgt"></a>&lt;string_view&gt;

クラステンプレート `basic_string_view` と関連する型および演算子を定義します。 (コンパイラオプション[std: c++ 17](../build/reference/std-specify-language-standard-version.md)以降が必要)

## <a name="syntax"></a>構文

```cpp
#include <string_view>
```

## <a name="remarks"></a>解説

テンプレートの特殊化の string_view ファミリは、読み取り専用の例外セーフな非所有のハンドルを、0の位置にあるシーケンスの最初の要素を使用して、文字列のようなオブジェクトの文字データに効率的に渡す方法を提供します。 型 `string_view` (の typedef) の関数パラメーター `basic_string_view<char>` `std::string` ** \* **では、などの引数を受け取ることができます。このような引数には、の暗黙的な変換が定義されているナロー文字が含まれ `string_view` ます。 同様に `wstring_view` 、、、またはのパラメーターは、 `u16string_view` `u32string_view` 暗黙的な変換が定義されている任意の文字列型を受け入れることができます。 詳細については、「 [Basic_string_view クラス](../standard-library/basic-string-view-class.md)」を参照してください。

### <a name="typedefs"></a>Typedefs

|型名|説明|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|`basic_string_view`型の要素を持つクラステンプレートの特殊化 **`char`** 。|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|`basic_string_view`型の要素を持つクラステンプレートの特殊化 **`wchar_t`** 。|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|`basic_string_view`型の要素を持つクラステンプレートの特殊化 **`char16_t`** 。|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|`basic_string_view`型の要素を持つクラステンプレートの特殊化 **`char32_t`** 。|

### <a name="operators"></a>オペレーター

演算子は、 \<string_view> `string_view` オブジェクトを変換可能な文字列型のオブジェクトと比較できます。

|演算子|Description|
|-|-|
|[operator! =](../standard-library/string-view-operators.md#op_neq)|演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。|
|[operator = =](../standard-library/string-view-operators.md#op_eq_eq)|演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。|
|[<演算子](../standard-library/string-view-operators.md#op_lt)|演算子の左側のオブジェクトが右側のオブジェクトより小さいかどうかをテストします。|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|演算子の左側のオブジェクトが右側のオブジェクト以下かどうかを調べます。|
|[<演算子\<](../standard-library/string-view-operators.md#op_lt_lt)|を出力ストリームに挿入するテンプレート関数 `string_view` 。|
|[>演算子](../standard-library/string-view-operators.md#op_gt)|演算子の左側のオブジェクトが右側のオブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|演算子の左側のオブジェクトが右側のオブジェクト以上であるかどうかを調べます。|

### <a name="literals"></a>リテラル

|演算子|Description|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|`string_view` `wstring_view` `u16string_view` `u32string_view` 追加先の文字列リテラルの型に応じて、、、、またはを構築します。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_string_view クラス](../standard-library/basic-string-view-class.md)|任意の文字に似たオブジェクトのシーケンスに読み取り専用のビューを提供するクラステンプレート。|
|[hash](string-view-hash.md)|String_view のハッシュ値を生成する関数オブジェクト。|

## <a name="requirements"></a>必要条件

- **ヘッダー:**\<string_view>

- **名前空間:** std

- **コンパイラオプション:** std: c++ 17 (またはそれ以降)

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
