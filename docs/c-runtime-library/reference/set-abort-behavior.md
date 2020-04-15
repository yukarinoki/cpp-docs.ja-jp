---
title: _set_abort_behavior
ms.date: 4/2/2020
api_name:
- _set_abort_behavior
- _o__set_abort_behavior
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: fd3a3c2f99d1702cdccf68328c2122b965b2d078
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337869"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

プログラムが異常終了した場合に実行するアクションを指定します。

> [!NOTE]
> テストまたはデバッグのシナリオを除き[、Microsoft](abort.md)ストア アプリをシャットダウンするために中止関数を使用しないでください。 ストア アプリを閉じるプログラムまたは UI の方法は、 [Microsoft Store のポリシー](/legal/windows/agreements/store-policies)に従って許可されていません。 詳しくは[、UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)に関する情報をご覧ください。

## <a name="syntax"></a>構文

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
[中止](abort.md)フラグの新しい値。

*mask*<br/>
[設定するフラグ](abort.md)ビットを中止するためのマスク。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>解説

**_WRITE_ABORT_MSG**と **_CALL_REPORTFAULT**の 2 つの[中止](abort.md)フラグがあります。 **_WRITE_ABORT_MSG**は、プログラムが異常終了したときに、役立つテキスト・メッセージを印刷するかどうかを判別します。 このメッセージは、アプリケーションが[abort](abort.md)関数を呼び出したことを示します。 既定の動作はメッセージを表示することです。 **_CALL_REPORTFAULT**が設定されている場合、Watson クラッシュ ダンプが生成され[、abort](abort.md)が呼び出されたときに報告されることを指定します。 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>関連項目

[中止](abort.md)<br/>
