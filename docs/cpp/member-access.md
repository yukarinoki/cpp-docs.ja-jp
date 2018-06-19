---
title: メンバー アクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- pointers, smart
- member access, overloaded operators
- operator overloading [C++], member access operators
- smart pointers, definition
- smart pointers
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8896e473f1a419f24636d7c503924b51426be24
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420088"
---
# <a name="member-access"></a>メンバー アクセス
メンバー アクセス演算子をオーバー ロードがクラス メンバーへのアクセスを制御できます (**->**)。 この演算子は、この使用方法では単項演算子と見なされ、オーバーロードされる演算子関数は、クラス メンバー関数である必要があります。 したがって、このような関数の宣言は次のとおりです。  
  
## <a name="syntax"></a>構文  
  
```  
  
class-type *operator->()  
```  
  
## <a name="remarks"></a>コメント  
 ここで*クラス型*このオペレーターが所属するクラスの名前を指定します。 メンバー アクセス演算子関数は、非静的メンバー関数である必要があります。  
  
 この演算子は、逆参照やカウントの使用の前にポインターを検証する "スマート ポインター" を実装するために使用されます (多くの場合はポインターの逆参照演算子と共に)。  
  
 **.** メンバー アクセス演算子はオーバー ロードできません。  
  
## <a name="see-also"></a>関連項目  
 [演算子のオーバーロード](../cpp/operator-overloading.md)