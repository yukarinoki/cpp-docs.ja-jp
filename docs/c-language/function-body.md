---
title: 関数本体
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C], syntax
- variables, function syntax
- function definitions, function body
- function body
ms.assetid: f7e74822-fac8-4dc8-8f3a-2b1611da4640
ms.openlocfilehash: 064e630d5ca74476c79522e39130e75f741d8946
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463688"
---
# <a name="function-body"></a>関数本体

"*関数本体*" は、関数が何を行うかを指定するステートメントを含む複合ステートメントです。

## <a name="syntax"></a>構文

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* は Microsoft 固有の仕様 \*/

*compound-statement*: /\* 関数本体 \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{** *declaration-list*<sub>opt</sub> *statement-list*<sub>opt</sub> **}**

関数本体で宣言された変数 ("*ローカル変数*") は、他の指定がない限り、**auto** ストレージ クラスになります。 関数が呼び出されると、ローカル変数のストレージが作成され、ローカルの初期化が実行されます。 実行制御は、*compound-statement* の最初のステートメントに渡され、**return** ステートメントが実行されるか、関数本体の終端に到達するまで続行されます。 次に、関数が呼び出された位置に制御が戻ります。

関数が値を返す場合は、式を含む **return** ステートメントが実行される必要があります。 関数の戻り値は、**return** ステートメントが実行されない場合や、**return** ステートメントに式が含まれない場合は、未定義となります。

## <a name="see-also"></a>参照

[C 関数の定義](../c-language/c-function-definitions.md)