---
title: swap 関数 (auto_gcroot) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
dev_langs:
- C++
helpviewer_keywords:
- swap function
ms.assetid: 2fe8146b-a7f7-445a-9ae9-53b5556be701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 308f909e2a863f2d08feb6ff688cddf61b0347b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165153"
---
# <a name="swap-function-autogcroot"></a>swap 関数 (auto_gcroot)
1 つの間でオブジェクトを交換`auto_gcroot`別とします。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename _element_type>  
void swap(  
   auto_gcroot<_element_type> & _left,  
   auto_gcroot<_element_type> & _right  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_left`  
 `auto_gcroot`。  
  
 `_right`  
 別`auto_gcroot`です。  
  
## <a name="example"></a>例  
  
```  
// msl_swap_auto_gcroot.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s1 = "string one";  
   auto_gcroot<String^> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
```Output  
s1 = 'string one', s2 = 'string two'  
s1 = 'string two', s2 = 'string one'  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー ファイル** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>関連項目  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot::swap](../dotnet/auto-gcroot-swap.md)