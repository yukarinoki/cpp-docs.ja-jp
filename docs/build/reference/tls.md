---
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: 1760e94046a950f67d3c3fd7ef13aa40ca7de47a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417789"
---
# <a name="tls"></a>/TLS

実行可能ファイルから IMAGE_TLS_DIRECTORY 構造が表示されます。

## <a name="remarks"></a>Remarks

や TLS 構造体のフィールドと TLS のコールバック関数のアドレス TLS を表示します。

プログラムではスレッド ローカル ストレージを使用しない場合、そのイメージには、TLS の構造は含まれません。  参照してください[スレッド](../../cpp/thread.md)詳細についてはします。

IMAGE_TLS_DIRECTORY は、winnt.h で定義されます。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)
