---
title: _get_purecall_handler、_set_purecall_handler
ms.date: 11/04/2016
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 0009b4bc1c7bf70bd84b9a82ecdc8643789e8164
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646364"
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler、_set_purecall_handler

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
純粋仮想関数が呼び出されたときに呼び出される関数。 A **_purecall_handler**関数は void 戻り値の型である必要があります。

## <a name="return-value"></a>戻り値

前の **_purecall_handler**します。 返します**nullptr**以前のハンドラーがない場合。

## <a name="remarks"></a>Remarks

**_Get_purecall_handler**と **_set_purecall_handler**関数は Microsoft 固有の仕様と C++ コードにのみ適用されます。

純粋仮想関数には実装がないため、この関数への呼び出しはエラーになります。 既定では、純粋仮想関数が呼び出されるとコンパイラによってエラー ハンドラー関数を呼び出すコードが生成され、プログラムが終了します。 純粋仮想関数の呼び出し用に独自のエラー ハンドラー関数をインストールして呼び出しをキャッチし、デバッグまたはレポート作成に使用することができます。 エラー ハンドラーを使用するを持つ関数を作成、 **_purecall_handler**のシグネチャを使用して **_set_purecall_handler**を現在のハンドラーします。

1 つしかないため、 **_purecall_handler**を呼び出すと、各プロセスの **_set_purecall_handler**すべてのスレッドをすぐに影響します。 ハンドラーは、すべてのスレッドでの最後の呼び出し元によって設定されます。

既定の動作を復元するには、呼び出す **_set_purecall_handler**を使用して、 **nullptr**引数。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_get_purecall_handler**、 **_set_purecall_handler**|\<cstdlib> または \<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
