---
title: call_in_appdomain 関数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: 567b6d8fe9412e58f21de9a1031ec54c4bc01cdc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230897"
---
# <a name="call_in_appdomain-function"></a>call_in_appdomain 関数

指定されたアプリケーションドメインで関数を実行します。

## <a name="syntax"></a>構文

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>パラメーター

*appdomainId*<br/>
関数を呼び出す appdomain。

*voidFunc*<br/>
**`void`** N 個のパラメーターを受け取る関数へのポインター (0 <= n <= 15)。

*非 Voidfunc*<br/>
N 個のパラメーターを受け取る非関数へのポインター **`void`** (0 <= N <= 15)。

*arg1...argN*<br/>
`voidFunc`他の appdomain に渡される 0 ~ 15 個 `nonvoidFunc` のパラメーター。

## <a name="return-value"></a>戻り値

`voidFunc` `nonvoidFunc` 指定したアプリケーションドメインでまたはを実行した結果。

## <a name="remarks"></a>解説

に渡される関数の引数を `call_in_appdomain` CLR 型にすることはできません。

## <a name="example"></a>例

```cpp
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>出力

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\appdomain.h>

**名前空間**msclr
