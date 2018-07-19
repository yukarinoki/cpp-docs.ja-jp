---
title: EDITBIN リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c20191fdb133fe09ed4f6a462cd777098acd5f05
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372309"
---
# <a name="editbin-reference"></a>EDITBIN リファレンス
Microsoft COFF Binary ファイル エディター (EDITBIN です。EXE) では、オブジェクト ファイル形式 COFF (Common) のバイナリ ファイルを変更します。 EDITBIN を使用して、オブジェクト ファイル、実行可能ファイル、およびダイナミック リンク ライブラリ (DLL) を変更することができます。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 EDITBIN はにより生成されるファイルで使用するため使用できません、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。 /GL で生成されたバイナリ ファイルに変更を加えるには、再コンパイルとリンクで行う必要があります。  
  
-   [EDITBIN コマンドライン](../../build/reference/editbin-command-line.md)  
  
-   [EDITBIN オプション](../../build/reference/editbin-options.md)  
  
## <a name="see-also"></a>関連項目  
 [C/C++ のビルド ツール](../../build/reference/c-cpp-build-tools.md)