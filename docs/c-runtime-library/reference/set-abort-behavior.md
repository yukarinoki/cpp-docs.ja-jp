---
title: _set_abort_behavior
ms.date: 1/02/2018
apiname:
- _set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: 8b36a771a3694c6d01573d619990743c7ddc0f3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643054"
---
# <a name="setabortbehavior"></a>_set_abort_behavior

プログラムが異常終了した場合に実行するアクションを指定します。

> [!NOTE]
> 使用しないでください、[中止](abort.md)関数をテストまたはデバッグ シナリオにを除き、Microsoft Store アプリをシャット ダウンします。 ストア アプリを終了するプログラムや UI の方法はに従って許可されていません、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)します。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)します。

## <a name="syntax"></a>構文

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
新しい値、[中止](abort.md)フラグ。

*マスク*<br/>
マスク、[中止](abort.md)フラグのビットを設定します。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>Remarks

2 つ[中止](abort.md)フラグ: **_WRITE_ABORT_MSG**と **_CALL_REPORTFAULT**します。 **_WRITE_ABORT_MSG**プログラムが異常終了したときに、テキスト メッセージが印刷されるかどうかを決定します。 メッセージは、アプリケーションが呼び出されていることを示す、[中止](abort.md)関数。 既定の動作はメッセージを表示することです。 **_CALL_REPORTFAULT**場合は、設定、報告されたときにワトソン クラッシュ ダンプが生成されることを指定します[中止](abort.md)が呼び出されます。 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[abort](abort.md)<br/>
