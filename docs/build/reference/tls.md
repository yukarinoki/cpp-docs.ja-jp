---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: c125a6439e6cda2159a8bde2317528e667eaf310
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532637"
---
# <a name="tls"></a>/TLS

実行可能ファイルから IMAGE_TLS_DIRECTORY 構造が表示されます。

## <a name="remarks"></a>Remarks

や TLS 構造体のフィールドと TLS のコールバック関数のアドレス TLS を表示します。

プログラムではスレッド ローカル ストレージを使用しない場合、そのイメージには、TLS の構造は含まれません。  参照してください[スレッド](../../cpp/thread.md)詳細についてはします。

IMAGE_TLS_DIRECTORY は、winnt.h で定義されます。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)