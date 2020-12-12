---
description: '詳細については、「方法: 固定ポインターと値型を宣言する」を参照してください。'
title: '方法 : 固定ポインターと値型を宣言する'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
ms.openlocfilehash: abbb085a9d85870d43ad00687b30e0f395186ba2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119292"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>方法 : 固定ポインターと値型を宣言する

値型を暗黙的にボックス化できます。 その後、値型オブジェクト自体への固定ポインターを宣言し、ボックス化された値型に対して **pin_ptr** を使用できます。

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

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)
