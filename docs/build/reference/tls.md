---
title: -TLS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /TLS
dev_langs:
- C++
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 78f485a783dbe8b5fe9a49ed3100754115bf50b8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714676"
---
# <a name="tls"></a>/TLS

実行可能ファイルから IMAGE_TLS_DIRECTORY 構造が表示されます。

## <a name="remarks"></a>Remarks

や TLS 構造体のフィールドと TLS のコールバック関数のアドレス TLS を表示します。

プログラムではスレッド ローカル ストレージを使用しない場合、そのイメージには、TLS の構造は含まれません。  参照してください[スレッド](../../cpp/thread.md)詳細についてはします。

IMAGE_TLS_DIRECTORY は、winnt.h で定義されます。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](../../build/reference/dumpbin-options.md)