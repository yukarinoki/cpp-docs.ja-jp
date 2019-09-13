---
title: _set_abort_behavior
ms.date: 01/02/2018
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
ms.openlocfilehash: b72a485287684fc85f1e232e89774e07a5e3f42b
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927488"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

プログラムが異常終了した場合に実行するアクションを指定します。

> [!NOTE]
> テストシナリオまたはデバッグシナリオ以外では、 [abort](abort.md)関数を使用して Microsoft Store アプリをシャットダウンしないでください。 プログラムまたは UI がストアアプリを閉じる方法は、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)によっては許可されていません。 詳細については、「 [UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)」を参照してください。

## <a name="syntax"></a>構文

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>パラメーター

*flags*<br/>
[中止](abort.md)フラグの新しい値。

*隠す*<br/>
設定する[abort](abort.md)フラグビットのマスク。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>Remarks

[Abort](abort.md)フラグには **、次の**2 つのフラグがあります。 プログラムが異常終了したときに、役に立つテキストメッセージを出力するかどうか**を指定します。 (_d** ) このメッセージは、アプリケーションが[abort](abort.md)関数を呼び出したことを示しています。 既定の動作はメッセージを表示することです。 設定した場合は、Watson クラッシュダンプが生成され、 [abort](abort.md)が呼び出されたときに報告されます。 ( **_d)** 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

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
