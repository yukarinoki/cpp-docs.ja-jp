---
description: '詳細については、次を参照してください: _endthread、_endthreadex'
title: _endthread、_endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: ef74cac4cbe23a021ed8d796f92f2767695eb08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332834"
---
# <a name="_endthread-_endthreadex"></a>_endthread、_endthreadex

スレッドを終了します。 **_endthread** は **_beginthread** によって作成されたスレッドを終了し  **_endthreadex** **_beginthreadex** によって作成されたスレッドを終了します。

## <a name="syntax"></a>構文

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>パラメーター

*retval*<br/>
スレッド終了コード。

## <a name="remarks"></a>解説

**_Endthread** または **_endthreadex** を明示的に呼び出してスレッドを終了できます。ただし、 **_endthread** または **_endthreadex** は、 **_beginthread** または **_beginthreadex** にパラメーターとして渡されたルーチンからスレッドが戻ったときに、自動的に呼び出されます。 **Endthread** または **_endthreadex** を呼び出すことによってスレッドを終了すると、スレッドに割り当てられたリソースを適切に復旧できます。

> [!NOTE]
> Libcmt.lib にリンクする実行可能ファイルでは、Win32 の [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API を呼び出さないでください。呼び出すと、割り当てられたリソースをランタイム システムで再利用することができなくなります。 **_endthread** と **_endthreadex** は、割り当てられているスレッドリソースを解放し、 **exitthread** を呼び出します。

**_endthread** によって、スレッドハンドルが自動的に閉じられます。 (この動作は、Win32 **Exitthread** API とは異なります)。したがって、 **_beginthread** と **_endthread** を使用する場合は、Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API を呼び出してスレッドハンドルを明示的に終了しないでください。

Win32 **exitthread** API と同様に、 **_endthreadex** はスレッドハンドルを閉じません。 したがって、 **_beginthreadex** と **_endthreadex** を使用する場合は、Win32 **CloseHandle** API を呼び出してスレッドハンドルを閉じる必要があります。

> [!NOTE]
> **_endthread** と **_endthreadex** により、スレッドで保留中の C++ デストラクターは呼び出されません。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。

## <a name="example"></a>例

[_beginthread](beginthread-beginthreadex.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread、_beginthreadex](beginthread-beginthreadex.md)<br/>
