---
title: Windows Sockets クラス |Microsoft Docs
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
ms.openlocfilehash: 893fa525b04376cde0e96f280c95e6bfd1243946
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439979"
---
# <a name="windows-sockets-classes"></a>Windows Sockets クラス

Windows ソケットは、2 台のコンピューター間で通信するネットワーク プロトコルに依存しない方法を提供します。 これらのソケットを同期することができます (プログラムは、通信が完了するまで待機する) または非同期 (プログラムの継続での通信が行われている)。

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
シン ラッパーで Windows ソケット API をカプセル化します。

[CSocket](../mfc/reference/csocket-class.md)<br/>
高いレベルの抽象化から派生した`CAsyncSocket`します。 同期的に動作します。

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
提供、 `CFile` Windows ソケット インターフェイス。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

