---
title: 関数本体
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 2ae73ab4ca91e06e3b6cd41166a8d05ae0857e4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229702"
---
# <a name="function-body"></a>関数本体

"*関数本体*" は、関数が何を行うかを指定するステートメントを含む複合ステートメントです。

## <a name="syntax"></a>構文

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* は Microsoft 固有の仕様です \*/

*compound-statement*: /\* 関数本体 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

関数本体で宣言された変数 ("*ローカル変数*") は、他の指定がない限り、 **`auto`** ストレージ クラスになります。 関数が呼び出されると、ローカル変数のストレージが作成され、ローカルの初期化が実行されます。 実行制御は、*compound-statement* の最初のステートメントに渡され、 **`return`** ステートメントが実行されるか、関数本体の終端に到達するまで続行されます。 次に、関数が呼び出された位置に制御が戻ります。

関数によって値が返される場合は、式を含む **`return`** ステートメントが実行される必要があります。 **`return`** ステートメントが実行されない場合、または **`return`** ステートメントに式が含まれない場合、関数の戻り値は未定義です。

## <a name="see-also"></a>関連項目

[C 関数の定義](../c-language/c-function-definitions.md)
