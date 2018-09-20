---
title: auto_gcroot::get |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::get
- msclr.auto_gcroot.get
- auto_gcroot::get
- auto_gcroot.get
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot::get
ms.assetid: 0e922019-1cf5-4220-b5ab-6c4a2a6b40ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0805205c5d8b6886d743f0e950aaa6af3ec964e1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393270"
---
# <a name="autogcrootget"></a>auto_gcroot::get

含まれるオブジェクトを取得します。

## <a name="syntax"></a>構文

```cpp
_element_type get() const;
```

## <a name="return-value"></a>戻り値

含まれるオブジェクト。

## <a name="example"></a>例

```cpp
// msl_auto_gcroot_get.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ){
      Console::WriteLine( "in ClassA constructor:" + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "in ClassA destructor:" + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

void PrintA( ClassA^ a ) {
   a->PrintHello();
}

int main() {
   auto_gcroot<ClassA^> a = gcnew ClassA( "first" );
   a->PrintHello();

   ClassA^ a2 = a.get();
   a2->PrintHello();

   PrintA( a.get() );
}
```

```Output
in ClassA constructor:first
Hello from first A!
Hello from first A!
Hello from first A!
in ClassA destructor:first
```

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[auto_gcroot のメンバー](../dotnet/auto-gcroot-members.md)