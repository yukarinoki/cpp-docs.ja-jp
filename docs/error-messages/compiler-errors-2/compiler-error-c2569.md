---
title: コンパイラ エラー C2569 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2569
dev_langs:
- C++
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4869f13d972cea80bd590633b3aae2ea0c96f392
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230343"
---
# <a name="compiler-error-c2569"></a>コンパイラ エラー C2569
'EnumOrUnion': 列挙および共用体は基底クラスとして使用できません  
  
 指定された共用体または列挙型を派生させる必要があります、クラスまたは構造体を union または列挙型を変更します。  
  
 次の例では、C2569 が生成されます。  
  
```  
// C2569.cpp  
// compile with: /c  
union ubase {};  
class cHasPubUBase : public ubase {};   // C2569  
// OK  
struct sbase {};  
class cHasPubUBase : public sbase {};  
```