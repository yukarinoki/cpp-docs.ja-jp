---
title: '方法: 固定ポインターの宣言と型の値 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c2dbb4bcbd1b6c76d00356535a9c99d983c1096
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40019879"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>方法 : 固定ポインターと値型を宣言する
値の型を暗黙的にボックス化することができます。 使用して、値型のオブジェクトへの固定ポインターを宣言し、 **pin_ptr**ボックス化された値の型にします。  
  
## <a name="example"></a>例  
  
### <a name="code"></a>コード  
  
```cpp  
// pin_ptr_value.cpp  
// compile with: /clr  
value struct V {  
   int i;  
};  
  
int main() {  
   V ^ v = gcnew V;   // imnplicit boxing  
   v->i=8;  
   System::Console::WriteLine(v->i);  
   pin_ptr<V> mv = &*v;  
   mv->i = 7;  
   System::Console::WriteLine(v->i);  
   System::Console::WriteLine(mv->i);  
}  
```  
  
```Output  
8  
7  
7  
```  
  
## <a name="see-also"></a>関連項目  
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)