---
title: /APPCONTAINER (ストア アプリが UWP/microsoft) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ca1a3ed5adaada689d374eeb3e67bae6c989e0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369293"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft ストア アプリ)
リンカーがアプリ コンテナーで実行される必要がある実行可能イメージを生成するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>コメント  
 既定では、/APPCONTAINER は無効になっています。  
  
 このオプションは、実行可能ファイルを変更し、appcontainer プロセス分離環境でアプリが実行される必要があるかどうかを示します。 Appcontainer 環境で実行する必要があるアプリの/APPCONTAINER を指定 — など、ユニバーサル Windows プラットフォーム (UWP) アプリまたは Windows Phone 8.x アプリ。 (オプションは設定に自動的に Visual Studio でテンプレートからユニバーサル Windows アプリを作成する場合)。デスクトップ アプリケーションでは、/APPCONTAINER:NO を指定するか、オプションを省略します。  
  
 /APPCONTAINER オプションは [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] で導入されました。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  展開して、**構成プロパティ**ノード。  
  
3.  展開して、**リンカー**ノード。  
  
4.  選択、**コマンドライン**プロパティ ページ。  
  
5.  **追加オプション**、入力`/APPCONTAINER`または`/APPCONTAINER:NO`です。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)