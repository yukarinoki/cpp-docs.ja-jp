---
title: auto_gcroot::auto_gcroot
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::auto_gcroot
- auto_gcroot::auto_gcroot
- auto_gcroot.auto_gcroot
- msclr.auto_gcroot.auto_gcroot
helpviewer_keywords:
- auto_gcroot::auto_gcroot
ms.assetid: 27faa42a-64ea-4d31-836f-073a55145735
ms.openlocfilehash: ea6772e2e4189b978aad2f14b048937bee4b1c90
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527414"
---
# <a name="autogcrootautogcroot"></a>auto_gcroot::auto_gcroot

`auto_gcroot`コンス トラクター。

## <a name="syntax"></a>構文

```cpp
auto_gcroot(
   _element_type _ptr = nullptr
);
auto_gcroot(
   auto_gcroot<_element_type> & _right
);
template<typename _other_type>
auto_gcroot(
   auto_gcroot<_other_type> & _right
);
```

#### <a name="parameters"></a>パラメーター

*_ptr*<br/>
所有するオブジェクト。

*(_r)*<br/>
既存の `auto_gcroot`。

## <a name="remarks"></a>Remarks

構築するときに、`auto_gcroot`既存の`auto_gcroot`、既存の`auto_gcroot`を新しいオブジェクトの所有権を譲渡する前に、そのオブジェクトを解放`auto_gcroot`します。

## <a name="example"></a>例

```cpp
// msl_auto_gcroot_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class RefClassA {
protected:
   String^ m_s;
public:
   RefClassA(String^ s) : m_s(s) {
      Console::WriteLine( "in RefClassA constructor: " + m_s );
   }
   ~RefClassA() {
      Console::WriteLine( "in RefClassA destructor: " + m_s );
   }

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class RefClassB : RefClassA {
public:
   RefClassB( String^ s ) : RefClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

class ClassA { //unmanaged class
private:
   auto_gcroot<RefClassA^> m_a;

public:
   ClassA() : m_a( gcnew RefClassA( "unmanaged" ) ) {}
   ~ClassA() {} //no need to delete m_a

   void DoSomething() {
      m_a->PrintHello();
   }
};

int main()
{
   {
      ClassA a;
      a.DoSomething();
   } // a.m_a is automatically destroyed as a goes out of scope

   {
      auto_gcroot<RefClassA^> a(gcnew RefClassA( "first" ) );
      a->PrintHello();
   }

   {
      auto_gcroot<RefClassB^> b(gcnew RefClassB( "second" ) );
      b->PrintHello();
      auto_gcroot<RefClassA^> a(b); //construct from derived type
      a->PrintHello();
      auto_gcroot<RefClassA^> a2(a); //construct from same type
      a2->PrintHello();
   }

   Console::WriteLine("done");
}
```

```Output
in RefClassA constructor: unmanaged
Hello from unmanaged A!
in RefClassA destructor: unmanaged
in RefClassA constructor: first
Hello from first A!
in RefClassA destructor: first
in RefClassA constructor: second
Hello from second B!
Hello from second A!
Hello from second A!
in RefClassA destructor: second
done
```

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[auto_gcroot のメンバー](../dotnet/auto-gcroot-members.md)<br/>
[auto_gcroot::attach](../dotnet/auto-gcroot-attach.md)<br/>
[auto_gcroot::operator=](../dotnet/auto-gcroot-operator-assign.md)<br/>
[auto_gcroot::~auto_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)