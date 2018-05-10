---
title: インポートのバインド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7519fb18ac7f24e79a5f7f664cb35f8eb5b3fd77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="binding-imports"></a>インポートのバインド
既定のリンカー動作では、遅延読み込みされた DLL のバインド可能なインポート アドレス テーブルを作成します。 ヘルパー関数が呼び出す代わりに、バインドされた情報を使用しようとして、DLL がバインドされている場合**GetProcAddress**参照されているインポートごとにします。 タイムスタンプまたは優先アドレスが一致しない場合、読み込まれた DLL のヘルパー関数とバインドされたインポート アドレス テーブルが古すぎますが存在しないかのように続行されます。  
  
 DLL の遅延読み込みしたインポートをバインドしない場合を指定する[/delay](../../build/reference/delay-delay-load-import-settings.md): リンカーのコマンドラインでは防止バインドのインポート アドレス テーブル、イメージ ファイルに領域を生成し、使用できます。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)