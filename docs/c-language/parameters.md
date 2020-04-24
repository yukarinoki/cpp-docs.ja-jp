---
title: パラメーター
ms.date: 11/04/2016
helpviewer_keywords:
- arguments [C++], function
- function parameters
- parameters [C++]
- function arguments, vs. parameters
- parameters [C++], function
- functions [C], parameters
- function parameters, syntax
- ellipsis (...), parameters
- '... ellipsis'
ms.assetid: 8f2b8026-78b5-4e21-86a3-bf0f91f05689
ms.openlocfilehash: 78ad91ea86d81a3b6d888335ba7b78399a1d2aea
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032071"
---
# <a name="parameters"></a>パラメーター

引数は、関数呼び出しによって関数に渡される値の名前です。 パラメーターは、関数が受け取ることを想定している値です。 関数プロトタイプでは、関数名の後のかっこに、関数のすべてのパラメーターと型の一覧が含まれます。 パラメーター宣言は、パラメーターに格納されている値の型、サイズ、および識別子を指定します。

## <a name="syntax"></a>構文

*関数定義*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\**属性 seq*はマイクロソフト固有です。\*/

*宣言子*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ポインター*<sub>opt</sub> *直接宣言子*

*直接宣言子*: /\*関数宣言子\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接宣言子*  **(**  *パラメーター型リスト*  **)** /\*新しいスタイルの宣言子\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*直接宣言子*  **(**  *識別子リスト*<sub>の opt</sub> **)** /\*廃止形式宣言子\*/

*パラメータ型リスト*: /\*パラメータリスト\*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメータリスト* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメータリスト* **、..**

*パラメータリスト*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメータ宣言*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*パラメータリスト* **,**  *パラメータ宣言*

*parameter-declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *abstract-declarator*<sub>opt</sub>

*parameter-type-list* は、コンマで区切られたパラメーター宣言のシーケンスです。 パラメーター リストの各パラメーターの形式は次のようになります。

```C
[register]  type-specifier [declarator]
```

**auto** 属性で宣言された関数パラメーターでは、エラーが発生します。 パラメーターの識別子は、関数に渡される値を参照するために関数本体で使用されます。 プロトタイプでパラメーター名を指定できますが、名前は、宣言の最後でスコープから外れます。 したがって、関数定義で同じ方法または別の方法でパラメーター名を割り当てることができます。 これらの識別子は、関数本体の最も外側のブロックで再定義できませんが、パラメーター リストが外側のブロックであるかのように、内部の入れ子のブロックで再定義できます。

*parameter-type-list* の各識別子は、次の例に示すように、適切な型指定子が前に指定されている必要があります。

```C
void new( double x, double y, double z )
{
    /* Function body here */
}
```

パラメータリストに少なくとも1つのパラメータが含まれる場合、リストの末尾にはカンマが続き、3 つのピリオド **(,..**) が続きます。この構造は"省略記号表記"と呼ばれ、関数に対する可変数の引数を示します。 (詳細については[、可変個の引数を使用した呼び出し](../c-language/calls-with-a-variable-number-of-arguments.md)を参照してください。ただし、関数の呼び出しには、最後のコンマの前にパラメーターがある数の引数が少なくとも必要です。

引数が関数に渡されない場合、パラメーターのリストはキーワード `void` で置き換えられます。 この `void` の使い方は、型指定子としての使い方とは異なります。

省略記号表記の使用を含むパラメーターの順序と型は、すべての関数宣言 (存在する場合) および関数定義で同じである必要があります。 通常の算術変換が対応するパラメーターの型と代入互換性を持つ必要があった後の引数の型 ([算術変換については、通常の算術](../c-language/usual-arithmetic-conversions.md)変換を参照してください。省略記号の後の引数はチェックされません。 パラメーターは、基本の構造体、共用体、ポインター、または配列型を持つことができます。

コンパイラは、必要に応じて、パラメーターごと、引数ごとに、通常の算術変換を個別に実行します。 変換後、`int` より短いパラメーターはなく、パラメーターの型をプロトタイプで **float** として明示的に指定しない限り、パラメーターに **float** 型はありません。 これは、たとえば、パラメーターを `char` として宣言すると、それを `int` として宣言する場合と同じ効果があることを意味しています。

## <a name="see-also"></a>関連項目

[C 関数の定義](../c-language/c-function-definitions.md)
