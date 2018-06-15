---
title: アプリのローカル フォルダーへの Visual C++ アプリケーションの配置 | Microsoft Docs
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33337910"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>チュートリアル: アプリケーションのローカル フォルダーへの Visual C++ アプリケーションの配置
ファイルをフォルダーにコピーして、Visual C ++ アプリケーションを配置する方法について説明します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
  
-   Visual Studio がインストールされているコンピューター。  
  
-   Visual C ++ ライブラリがない別のコンピューター。  
  
### <a name="to-deploy-an-application-to-an-application-local-folder"></a>アプリケーションをアプリケーションのローカル フォルダーに配置するには  
  
1.  「[チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)」の手順に従って、MFC ++ アプリケーションを作成してビルドします。  
  
2.  適切な MFC および C ランタイム (CRT) ライブラリ ファイルをコピーします。たとえば、x86 プラットフォームと Unicode サポートの場合は、\Program Files\Microsoft Visual Studio 10.0\VC\redist\x86\ から mfc100u.dll と msvcr100.dll をコピーし、MFC プロジェクトの \Release\ フォルダーに貼り付けます。 場合によってはコピーする必要がある他のファイルの詳細については、「[再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md)」を参照してください。  
  
3.  Visual C ++ ライブラリがない 2 台目のコンピューターで、MFC アプリケーションを実行します。  
  
    1.  \Release\ フォルダーの内容をコピーし、2 台目のコンピューター上のアプリケーション フォルダーに貼り付けます。  
  
    2.  2 台目のコンピューターでアプリケーションを実行します。  
  
     Visual C ++ ライブラリはアプリケーションのローカル フォルダーにあるため、アプリケーションは正常に実行されます。  
  
## <a name="see-also"></a>参照  
 [配置例](../ide/deployment-examples.md)