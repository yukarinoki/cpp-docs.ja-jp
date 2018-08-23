---
title: /APPCONTAINER (UWP/Microsoft Store アプリ) |Microsoft Docs
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
ms.openlocfilehash: eab6a9bd8ac37dec250739e3554c370726dce9eb
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589578"
---
# <a name="appcontainer-microsoft-store-app"></a>/APPCONTAINER (Microsoft Store アプリ)
リンカーがアプリ コンテナーで実行される必要がある実行可能イメージを生成するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/APPCONTAINER[:NO]  
```  
  
## <a name="remarks"></a>Remarks  
 既定では、/APPCONTAINER は無効になっています。  
  
 このオプションは、実行可能ファイルを変更し、appcontainer プロセス分離環境でアプリが実行される必要があるかどうかを示します。 Appcontainer 環境で実行する必要があるアプリの/APPCONTAINER を指定 — など、ユニバーサル Windows プラットフォーム (UWP) アプリまたは Windows Phone 8.x アプリ。 (オプションは設定に自動的に Visual Studio でテンプレートからユニバーサル Windows アプリを作成するときに)。デスクトップ アプリケーションでは、/APPCONTAINER:NO を指定するか、オプションを省略します。  
  
 /APPCONTAINER オプションは、Windows 8 で導入されました。  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **[構成プロパティ]** ノードを展開します。  
  
3.  展開、**リンカー**ノード。  
  
4.  選択、**コマンドライン**プロパティ ページ。  
  
5.  **追加オプション**、入力`/APPCONTAINER`または`/APPCONTAINER:NO`します。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)