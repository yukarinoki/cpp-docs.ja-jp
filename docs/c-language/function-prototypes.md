---
description: '詳細情報: 関数プロトタイプ'
title: 関数プロトタイプ
ms.date: 11/04/2016
helpviewer_keywords:
- function prototypes
- function return types, function prototypes
- data types [C], function return types
- functions [C], return types
- prototypes [C++], function
ms.assetid: d152f8e6-971e-432c-93ca-5a91400653c2
ms.openlocfilehash: d8e83e68daaa610387f3a23c06ad5ee49a8b3944
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151841"
---
# <a name="function-prototypes"></a>関数プロトタイプ

関数宣言を関数定義の前に挿入し、関数の名前、戻り値の型、ストレージ クラスとその他の属性を指定します。 プロトタイプにするには、関数宣言で、その関数の引数の型と識別子も指定する必要があります。

## <a name="syntax"></a>構文

*declaration*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers* *attribute-seq*<sub>opt</sub> *init-declarator-list*<sub>opt</sub> **;**

/\* *attribute-seq*<sub>opt</sub> は Microsoft 固有の仕様です \*/

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>

*init-declarator-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*init-declarator-list*  **,**  *init-declarator*

*init-declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declarator* **=** *initializer*

*declarator*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*pointer*<sub>opt</sub> *direct-declarator*

*direct-declarator*: /\* 関数宣言子 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *parameter-type-list*  **)**   /\* 新しい形式の宣言子 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*direct-declarator*  **(**  *identifier-list*<sub>opt</sub> **)**  /\* 古い形式の宣言子 \*/

プロトタイプは、右かっこのすぐ後のセミコロンで終了するため本体がないという点を除き、関数定義と同じ形式です。 いずれの場合も、戻り値の型は、関数定義で指定された戻り値の型と一致する必要があります。

関数プロトタイプには次の重要な用途があります。

- **`int`** 以外の型を返す関数の戻り値の型を設定します。 **`int`** 値を返す関数の場合、プロトタイプは必須ではありませんが、プロトタイプの使用をお勧めします。

- 完全なプロトタイプがない場合は標準変換が行われますが、型または引数の数とパラメーターの数は照合されません。

- プロトタイプは、関数を定義する前に、それらの関数へのポインターを初期化するために使用されます。

- パラメーター リストは、関数定義でパラメーターを持つ関数呼び出しの引数の対応を確認するために使用されます。

関数呼び出しがスタックに配置する引数の解釈は、各パラメーターの変換後の型によって決まります。 引数とパラメーターの間の型の不一致によって、スタックの引数が誤って解釈される場合があります。 たとえば、16 ビット コンピューターで 16 ビットのポインターが引数として渡され、 **`long`** パラメーターとして宣言されると、スタックの最初の 32 ビットは **`long`** パラメーターとして解釈されます。 このエラーにより、 **`long`** パラメーターだけでなく、後続のすべてのパラメーターで問題が発生します。 すべての関数の完全な関数プロトタイプを宣言すれば、この種のエラーを検出できます。

プロトタイプは、定義の前にある (または他のソース ファイルにある) 関数への呼び出しで引数の型と戻り値の型の不一致がチェックできるように関数の属性を設定します。 たとえば、プロトタイプで **`static`** ストレージ クラスの指定子を指定する場合、関数定義で **`static`** ストレージ クラスも指定する必要があります。

完全なパラメーター宣言 (`int a`) は、同じ宣言の抽象宣言子 ( **`int`** ) と混在させることができます。 たとえば、次の宣言は有効です。

```C
int add( int a, int );
```

プロトタイプには、引数として渡されたそれぞれの式の型と識別子を含めることができます。 ただし、このような識別子のスコープは、宣言の末尾までに限定されます。 プロトタイプは、引数の数が可変である、または渡す引数がないという事実も反映できます。 このようなリストがないと、不一致が検出されず、コンパイラはこれらに関する診断メッセージを生成できません。 型チェックの詳細については、「[引数](../c-language/arguments.md)」を参照してください。

Microsoft C コンパイラのプロトタイプ スコープは、 **/Za** コンパイラ オプションを指定してコンパイルした場合に ANSI に準拠します。 これは、プロトタイプ内で **`struct`** または **`union`** タグを宣言する場合、タグはグローバル スコープではなく、そのスコープに入ることを意味しています。 たとえば、ANSI 準拠のために **/Za** を指定してコンパイルする場合、この関数を呼び出すと常に型の不一致エラーが発生します。

```C
void func1( struct S * );
```

コードを修正するには、関数プロトタイプの前にグローバル スコープで **`struct`** または **`union`** を定義または宣言します。

```C
struct S;
void func1( struct S * );
```

**/Ze** では、タグは引き続きグローバル スコープで入力されます。

## <a name="see-also"></a>関連項目

[関数](../c-language/functions-c.md)
