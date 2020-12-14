---
description: 詳細情報:/TLS
title: /TLS
ms.date: 11/04/2016
f1_keywords:
- /TLS
helpviewer_keywords:
- /TLS dumpbin option
- -TLS dumpbin option
ms.assetid: 2b3f48f9-cac4-4351-b15c-2833b43bc709
ms.openlocfilehash: a21ef03210a65bb50899ba3907911272ac52b0db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229952"
---
# <a name="tls"></a>/TLS

実行可能ファイルから IMAGE_TLS_DIRECTORY 構造体を表示します。

## <a name="remarks"></a>解説

/Tls は、tls の構造体のフィールドと TLS コールバック関数のアドレスを表示します。

プログラムがスレッドローカルストレージを使用しない場合、そのイメージに TLS 構造は含まれません。  詳細については、「 [スレッド](../../cpp/thread.md) 」を参照してください。

IMAGE_TLS_DIRECTORY は、winnt.h で定義されています。

## <a name="see-also"></a>関連項目

[DUMPBIN オプション](dumpbin-options.md)
