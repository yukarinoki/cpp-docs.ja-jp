---
title: signal 定数
ms.date: 11/04/2016
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
ms.openlocfilehash: d26671b8c3d983e7f1c3fd559d8aa2029e3162fe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841143"
---
# <a name="signal-constants"></a>signal 定数

## <a name="syntax"></a>構文

```
#include <signal.h>
```

## <a name="remarks"></a>解説

`sig` 引数は、SIGNAL.H に定義されている以下のマニフェスト定数のいずれかにする必要があります。

|定数|説明|
|-|-|
|SIGABRT|異常終了。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  |
|SIGABRT_COMPAT|SIGABRT と同じ。 その他のプラットフォームとの互換性を維持します。  |
|SIGFPE|オーバーフロー、0 除算、無効な操作などの浮動小数点エラー。 既定のアクションでは、呼び出し元のプログラムを終了します。  |
|SIGILL|無効な命令。 既定のアクションでは、呼び出し元のプログラムを終了します。  |
|SIGINT|Ctrl + C 割り込み。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  |
|SIGSEGV|ストレージへの無効なアクセス。 既定のアクションでは、呼び出し元のプログラムを終了します。  |
|SIGTERM|プログラムに送信される終了要求。 既定のアクションでは、終了コード 3 で呼び出し元のプログラムを終了します。  |
|SIG_ERR|エラーが発生したことを示すシグナルからの戻り値の型。  |

## <a name="see-also"></a>関連項目

[signal](../c-runtime-library/reference/signal.md)<br/>
[発生](../c-runtime-library/reference/raise.md)<br/>
[グローバル定数](../c-runtime-library/global-constants.md)
