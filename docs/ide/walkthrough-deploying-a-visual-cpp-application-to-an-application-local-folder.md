---
title: アプリのローカル フォルダーへの Visual C アプリケーションの展開 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a02e585dc2b82c8b8ad675907e4205db6ad7279
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>チュートリアル: アプリケーションのローカル フォルダーへの Visual C++ アプリケーションの配置
そのフォルダーにファイルをコピーして Visual C アプリケーションを展開する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   Visual Studio がインストールされているコンピューター。  
  
-   Visual C ライブラリがない別のコンピューター。  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>アプリケーションのローカル フォルダーへのアプリケーションを展開するには  
  
1.  作成し、次の手順に従って、MFC アプリケーションをビルド[チュートリアル: プロジェクトを配置する、Visual C++ を使ったアプリケーション セットアップ](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)です。  
  
2.  適切な MFC および C ランタイム (CRT) ライブラリのファイル コピー — たとえば、x86 のプラットフォームと Unicode のサポート、コピー mfc100u.dll および \Program Files\Microsoft Visual Studio 10.0\VC\redist\x86\—and から msvcr100.dll に貼り付けるの \Release\ フォルダーMFC プロジェクト。 他のファイルをコピーする必要がありますの詳細については、次を参照してください。[再配布する Dll の決定](../ide/determining-which-dlls-to-redistribute.md)です。  
  
3.  Visual C ライブラリがない別のコンピューターには、MFC アプリケーションを実行します。  
  
    1.  \Release\ フォルダーの内容をコピーし、2 番目のコンピューター上のアプリケーション フォルダーに貼り付けます。  
  
    2.  2 番目のコンピューターでアプリケーションを実行します。  
  
     Visual C ライブラリがアプリケーションのローカル フォルダーにあるため、アプリケーションが正常に実行します。  
  
## <a name="see-also"></a>関連項目  
 [配置例](../ide/deployment-examples.md)