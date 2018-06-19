---
title: Windows Sockets クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.net
dev_langs:
- C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e370c8a5f9cb2fb42c3199dbc0d56b69d93dc35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382129"
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス
Windows ソケットは、2 台のコンピューター間の通信にネットワーク プロトコルに依存しない方法を提供します。 これらのソケットは同期していることができます (プログラムは、通信が終了するまで待機する) または非同期 (プログラムは、通信が起こっている間に実行が続行されます)。  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Thin ラッパーで Windows ソケット API をカプセル化します。  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 派生した上位レベルの抽象化`CAsyncSocket`です。 同期的に動作します。  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 提供、 `CFile` Windows ソケットへのインターフェイスです。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

