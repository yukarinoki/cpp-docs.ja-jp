---
description: '詳細については、次を参照してください: _get_purecall_handler、_set_purecall_handler'
title: _get_purecall_handler、_set_purecall_handler
ms.date: 11/04/2016
api_name:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
ms.openlocfilehash: 7971847c4ce0861db272ea3c722666b0ba0318d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339026"
---
# <a name="_get_purecall_handler-_set_purecall_handler"></a>_get_purecall_handler、_set_purecall_handler

純粋仮想関数呼び出しのエラー ハンドラーを取得または設定します。

## <a name="syntax"></a>構文

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>パラメーター

*function*<br/>
純粋仮想関数が呼び出されたときに呼び出される関数。 **_Purecall_handler** 関数の戻り値の型は void である必要があります。

## <a name="return-value"></a>戻り値

前の **_purecall_handler**。 **`nullptr`** 以前のハンドラーがなかった場合は、を返します。

## <a name="remarks"></a>解説

**_Get_purecall_handler** 関数と **_set_purecall_handler** 関数は、Microsoft 固有の関数であり、C++ コードにのみ適用されます。

純粋仮想関数には実装がないため、この関数への呼び出しはエラーになります。 既定では、純粋仮想関数が呼び出されるとコンパイラによってエラー ハンドラー関数を呼び出すコードが生成され、プログラムが終了します。 純粋仮想関数の呼び出し用に独自のエラー ハンドラーの関数をインストールして呼び出しをキャッチし、デバッグまたはレポート作成に使用することができます。 独自のエラーハンドラーを使用するには、 **_purecall_handler** シグネチャを持つ関数を作成し、 **_set_purecall_handler** を使用してそれを現在のハンドラーにします。

各プロセスには **_purecall_handler** が1つしかないので、を呼び出すと、すべてのスレッドが直ちに影響を受ける **_set_purecall_handler** ます。 ハンドラーは、すべてのスレッドでの最後の呼び出し元によって設定されます。

既定の動作を復元するには、引数を使用して **_set_purecall_handler** を呼び出し **`nullptr`** ます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_purecall_handler**、 **_set_purecall_handler**|\<cstdlib> または \<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>関連項目

[エラー処理](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
