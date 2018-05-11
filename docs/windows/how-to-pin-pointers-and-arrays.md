---
title: '方法: ポインターと配列をピン留め |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1cea9b1c7c6738c33f00e984aa8212d611b4aec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-pin-pointers-and-arrays"></a>方法 : ポインターと配列を固定する
マネージ オブジェクトで定義されている下位のオブジェクトをピン留めすると、オブジェクト全体をピン留めの効果があります。  たとえば、配列のいずれかの要素をピン留めすると場合、し、配列全体がもピン留めします。 ピン留めされた配列を宣言するための言語拡張機能はありません。 配列をピン留めするには、その要素の型とその要素のいずれかの暗証番号 (pin) への固定ポインターを宣言します。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```  
// pin_ptr_array.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
int main() {  
   array<Byte>^ arr = gcnew array<Byte>(4);  
   arr[0] = 'C';  
   arr[1] = '+';  
   arr[2] = '+';  
   arr[3] = '\0';  
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned  
   unsigned char * cp = p;  
  
   printf_s("%s\n", cp); // bytes pointed at by cp  
                         // will not move during call  
}  
```  
  
### <a name="output"></a>出力  
  
```  
++  
```  
  
## <a name="see-also"></a>関連項目  
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)