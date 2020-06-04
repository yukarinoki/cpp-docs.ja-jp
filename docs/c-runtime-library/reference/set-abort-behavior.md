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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 06f72597a384cc5c90b2e345e62e13dee96c4dca
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913132"
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

*mask*<br/>
設定する[abort](abort.md)フラグビットのマスク。

## <a name="return-value"></a>戻り値

フラグの元の値。

## <a name="remarks"></a>解説

[Abort](abort.md)フラグには、 **_WRITE_ABORT_MSG**と **_CALL_REPORTFAULT**の2つがあります。 **_WRITE_ABORT_MSG**は、プログラムが異常終了したときに役立つテキストメッセージを出力するかどうかを決定します。 このメッセージは、アプリケーションが[abort](abort.md)関数を呼び出したことを示しています。 既定の動作はメッセージを表示することです。 **_CALL_REPORTFAULT**に設定すると、Watson のクラッシュダンプが生成され、 [abort](abort.md)が呼び出されたときに報告されます。 既定では、クラッシュ ダンプのレポートは、非デバッグ ビルドで有効になっています。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

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

[取り消し](abort.md)<br/>
