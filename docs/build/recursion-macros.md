---
title: 再帰マクロ |Microsoft Docs
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
ms.openlocfilehash: f91a5f327686a522608b6eec9fd7106cbab00028
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702041"
---
# <a name="recursion-macros"></a>再帰マクロ

再帰マクロを使用すると、NMAKE を再帰的に呼び出します。 再帰的なセッションは、コマンドラインと環境変数マクロと Tools.ini の情報を継承します。 メイクファイルで定義された推論規則は継承しませんまたは**します。サフィックス**と**します。貴重な**仕様。 再帰 (nmake の) セッションにマクロを渡す再帰呼び出しの前に設定された環境変数を設定の再帰呼び出しするためのコマンドで、マクロを定義または Tools.ini でマクロを定義します。

|マクロ|定義|
|-----------|----------------|
|**作成**|NMAKE の呼び出しに最初に使用するコマンド。<br /><br /> $(MAKE) マクロは、nmake.exe への完全なパスを提供します。|
|**MAKEDIR**|NMAKE が呼び出されたときの現在のディレクトリ。|
|**MAKEFLAGS**|オプションは現在有効です。 として使用`/$(MAKEFLAGS)`します。  /F が含まれていないに注意してください。|

## <a name="see-also"></a>関連項目

[NMAKE の特殊マクロ](../build/special-nmake-macros.md)