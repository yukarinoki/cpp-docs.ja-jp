---
title: lock::operator! = |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- lock.operator!=
- msclr.lock.operator!=
- msclr::lock::operator!=
- lock::operator!=
dev_langs:
- C++
helpviewer_keywords:
- lock::operator!=
ms.assetid: ed1d674e-9ee9-4257-8a7e-2e3567d50222
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6b34eb410e05bd102f7a10205e57b3731b8f476d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130348"
---
# <a name="lockoperator"></a>lock::operator!=
非等値演算子。  
  
## <a name="syntax"></a>構文  
  
```  
template<class T> bool operator!=(  
   T t  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `t`  
 非等値を比較するオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 返します`true`場合`t`ロックのオブジェクトと異なります`false`それ以外の場合。  
  
## <a name="example"></a>例  
  
```  
// msl_lock_op_ineq.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
int main () {  
   Object^ o1 = gcnew Object;  
   Object^ o2 = gcnew Object;  
   lock l1(o1);  
   if (l1 != o2) {  
      Console::WriteLine("Inequal!");  
   }  
}  
```  
  
```Output  
Inequal!  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [lock のメンバー](../dotnet/lock-members.md)   
 [lock::operator==](../dotnet/lock-operator-equality.md)