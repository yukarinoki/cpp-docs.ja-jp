---
title: 文字の利点の移植性の設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- character sets [C++], benefits
- portability [C++], character sets
ms.assetid: bd60b925-1498-4e4f-897b-4c8ce66edcf7
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d1b78048baebfd89aed0ccc898c2bb9e3612525
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853818"
---
# <a name="benefits-of-character-set-portability"></a>文字セットにおける移植性の利点
現在しないアプリケーションの国際化する場合でも、MFC および C ランタイムの移植性の機能を使用する利点が得られます。  
  
-   柔軟な基本コードは、移植可能な方法でコーディングします。 後で移動できます簡単に Unicode や MBCS にします。  
  
-   Unicode を使用すると、Windows アプリケーションはより効率的です。 Windows では、Unicode を使用するためと、オペレーティング システムから渡される Unicode 以外の文字列変換される必要が、オーバーヘッドが発生します。  

  
## <a name="see-also"></a>関連項目  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [Unicode のサポート](../text/support-for-unicode.md)