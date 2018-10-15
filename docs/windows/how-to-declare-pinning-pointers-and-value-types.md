---
title: '方法: 固定ポインターの宣言と型の値 |Microsoft Docs'
ms.custom: ''
ms.date: 10/12/2018
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
ms.openlocfilehash: 2e724e468ec9c95a2404ea70c8666bc6880207ca
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327610"
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