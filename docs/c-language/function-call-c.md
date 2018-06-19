---
title: 関数呼び出し (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function calls, C functions
- functions [C], calling
- function calls
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49c9483cb6e556d5a8b174377c0dad666834c9e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384360"
---
# <a name="function-call-c"></a>関数呼び出し (C)
"関数呼び出し" は、呼び出される関数の名前または関数ポインターの値、および、関数に渡される省略可能な引数の値を含む式です。  
  
## <a name="syntax"></a>構文  
 *postfix-expression*:  
 *postfix-expression*  **(**  *argument-expression-list* opt **)**  
  
 *argument-expression-list*:  
 *assignment-expression*  
  
 *argument-expression-list*  **,**  *assignment-expression*  
  
 *postfix-expression* は、関数アドレス (たとえば、関数の識別子または関数ポインターの値) に評価される必要があります。*argument-expression-list* は、式の (コンマ区切りの) リストで、各式の値 ("引数") が関数に渡されます。 *argument-expression-list* 引数は空の場合もあります。  
  
 関数呼び出しの式は、関数の戻り値の値と型を持ちます。 関数は配列型のオブジェクトを返すことができません。 関数の戻り値の型が `void` (つまり、値を返さない関数であると宣言されている) の場合、関数呼び出し式も `void` 型になります  (詳細については、「[関数呼び出し](../c-language/function-calls.md)」を参照してください)。  
  
## <a name="see-also"></a>参照  
 [関数呼び出し演算子: ()](../cpp/function-call-operator-parens.md)