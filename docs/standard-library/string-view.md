---
title: '&lt;string_view&gt;'
ms.date: 04/18/2019
helpviewer_keywords:
- string_view header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
ms.openlocfilehash: 8952416cf37fc4d8d281d6ced9b8264495ec3799
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346980"
---
# <a name="ltstringviewgt"></a>&lt;string_view&gt;

クラス テンプレート定義`basic_string_view`関連のタイプとオペレーターとします。 (コンパイラ オプションが必要です[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)またはそれ以降)。

## <a name="syntax"></a>構文

```cpp
#include <string_view>
```

## <a name="remarks"></a>Remarks

テンプレートの特殊化の string_view ファミリは、任意の文字列のようなオブジェクトの位置 0 にあるシーケンスの最初の要素の文字データに読み取り専用、例外セーフ、所有している以外のハンドルを渡す効率的な方法を提供します。 型の関数パラメーター `string_view` (の typedef である`basic_string_view<char>`) などの引数を受け入れることができます`std::string`、 **char\***、または他の任意の文字列のようなクラスをナロー文字の暗黙的な変換`string_view`が定義されています。 パラメーターでは同様に、 `wstring_view`、`u16string_view`または`u32string_view`暗黙的な変換が定義されている任意の文字列型を受け入れることができます。 詳細については、次を参照してください。 [basic_string_view クラス](../standard-library/basic-string-view-class.md)します。

### <a name="typedefs"></a>Typedef

|型名|説明|
|-|-|
|[string_view](../standard-library/string-view-typedefs.md#string_view)|クラス テンプレートの特殊化`basic_string_view`型の要素を含む**char**します。|
|[wstring_view](../standard-library/string-view-typedefs.md#wstring_view)|クラス テンプレートの特殊化`basic_string_view`型の要素を含む**wchar_t**します。|
|[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)|クラス テンプレートの特殊化`basic_string_view`型の要素を含む`char16_t`します。|
|[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)|クラス テンプレートの特殊化`basic_string_view`型の要素を含む`char32_t`します。|

### <a name="operators"></a>演算子

\<String_view > 演算子を比較できる`string_view`文字列型のオブジェクトをオブジェクトの変換可能なのです。

|演算子|説明|
|-|-|
|[operator!=](../standard-library/string-view-operators.md#op_neq)|演算子の左側のオブジェクトが右側のオブジェクトと等しくないかどうかを調べます。|
|[operator==](../standard-library/string-view-operators.md#op_eq_eq)|演算子の左側のオブジェクトが右側のオブジェクトと等しいかどうかを調べます。|
|[operator<](../standard-library/string-view-operators.md#op_lt)|演算子の左側にあるオブジェクトがより小さい場合にテスト右側にあるオブジェクト。|
|[operator<=](../standard-library/string-view-operators.md#op_lt_eq)|演算子の左側のオブジェクトが右側のオブジェクト以下かどうかを調べます。|
|[operator<\<](../standard-library/string-view-operators.md#op_lt_lt)|挿入するテンプレート関数を`string_view`出力ストリームにします。|
|[operator>](../standard-library/string-view-operators.md#op_gt)|演算子の左側にあるオブジェクトが右側にあるオブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/string-view-operators.md#op_gt_eq)|演算子の左側のオブジェクトが右側のオブジェクト以上であるかどうかを調べます。|

### <a name="literals"></a>リテラル

|演算子|説明|
|-|-|
|[sv](../standard-library/string-view-operators.md#op_sv)|構築、 `string_view`、 `wstring_view`、 `u16string_view`、または`u32string_view`に応じて文字列リテラルの型が追加されます。|

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[basic_string_view クラス](../standard-library/basic-string-view-class.md)|任意の文字のようなオブジェクトのシーケンスに読み取り専用ビューを提供するクラス テンプレートです。|
|[hash](string-view-hash.md)|String_view のハッシュ値を生成する関数オブジェクト。|

## <a name="requirements"></a>必要条件

- **ヘッダー:** \<string_view >

- **名前空間:** std

- **コンパイラ オプション:** /std:c + + 17 (またはそれ以降)

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
