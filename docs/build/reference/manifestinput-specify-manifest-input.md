---
title: -MANIFESTINPUT (マニフェストの入力を指定してください) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: a0b0c21e-1f9b-4d8c-bb3f-178f57fa7f1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eecf1740855c2feef0d7cac4bbcc85ad95eade6f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="manifestinput-specify-manifest-input"></a>/MANIFESTINPUT (マニフェスト入力の指定)
マニフェスト入力ファイルをイメージに埋め込まれたマニフェストに含めるように指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/MANIFESTINPUT:filename  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 埋め込みマニフェストに含めるマニフェスト ファイル。  
  
## <a name="remarks"></a>コメント  
 **/MANIFESTINPUT**オプションを使用して実行可能イメージに埋め込みマニフェストを作成する入力ファイルのパスを指定します。 複数のマニフェスト入力ファイルがある場合は、スイッチを複数回使用します (入力ファイルごとに 1 回)。 マニフェスト入力ファイルは埋め込みマニフェストを作成するためにマージされます。 このオプションが必要、 **/manifest: 埋め込む**オプション。  
  
 このオプションは [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] で直接設定することはできません。 代わりに、使用、**追加のマニフェスト ファイル**に含める追加のマニフェスト ファイルを指定するプロジェクトのプロパティです。 詳細については、次を参照してください。[入力と出力、マニフェスト ツール、構成プロパティ、\<プロジェクト名 > プロパティ ページ ダイアログ ボックス](../../ide/input-and-output-manifest-tool.md)です。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)