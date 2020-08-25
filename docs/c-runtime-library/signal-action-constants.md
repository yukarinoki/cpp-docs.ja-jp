---
title: signal のアクション定数
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: a7448730501d6f3b50008966134f708ae99ddb5b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830762"
---
# <a name="signal-action-constants"></a>signal のアクション定数

割り込みシグナルを受信したときに実行されるアクションは、`func` の値によって異なります。

## <a name="syntax"></a>構文

```
#include <signal.h>
```

## <a name="remarks"></a>解説

`func` 引数は、関数のアドレス、または SIGNAL.H に定義されている以下のマニフェスト定数のいずれかにする必要があります。

|定数|説明|
|-|-|
| `SIG_DFL`  | システム既定の応答を使用します。 呼び出し元のプログラムがストリーム I/O を使用している場合、ランタイム ライブラリによって作成されるバッファーはフラッシュされません。  |
| `SIG_IGN`  | 割り込みシグナルを無視します。 プロセスの浮動小数点状態が未定義のままになるため、この値を `SIGFPE` に指定しないでください。  |
| `SIG_SGE`  | シグナルでエラーが発生したことを示します。  |
| `SIG_ACK`  | 受信確認を受け取ったことを示します。  |
| `SIG_ERR`  | エラーが発生したことを示すシグナルからの戻り値の型。  |

## <a name="see-also"></a>関連項目

[signal](../c-runtime-library/reference/signal.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)
