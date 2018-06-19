---
title: 再帰マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2759deaff6014cbba40c97f9d627baf6a800732f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368962"
---
# <a name="recursion-macros"></a>再帰マクロ
再帰マクロを使用すると、NMAKE を再帰的に呼び出します。 再帰的なセッションは、コマンドラインと環境変数マクロと Tools.ini の情報を継承します。 メイクファイルで定義された推論規則を引き継がないまたは**です。サフィックス**と**です。貴重な**仕様です。 再帰 (nmake の) セッションにマクロを渡すに再帰呼び出しの前に設定された環境変数を設定、再帰呼び出し用のコマンドでマクロを定義または Tools.ini でマクロを定義します。  
  
|マクロ|定義|  
|-----------|----------------|  
|**ください**|NMAKE の呼び出しに最初に使用するコマンド。<br /><br /> $(MAKE) マクロは、nmake.exe への完全なパスを提供します。|  
|**MAKEDIR**|NMAKE が呼び出されたときの現在のディレクトリ。|  
|**MAKEFLAGS**|現在有効になってオプションです。 として使用`/$(MAKEFLAGS)`です。  /F が含まれていないに注意してください。|  
  
## <a name="see-also"></a>関連項目  
 [NMAKE の特殊マクロ](../build/special-nmake-macros.md)