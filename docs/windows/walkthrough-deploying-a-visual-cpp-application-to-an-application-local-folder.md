---
description: '詳細については、「チュートリアル: アプリケーションローカルフォルダーへの Visual C++ アプリケーションの配置」を参照してください。'
title: アプリのローカル フォルダーへの Visual C++ アプリケーションの配置
ms.date: 04/23/2019
helpviewer_keywords:
- deploying Visual C++ applications
ms.assetid: 47a81c47-9dbe-47c6-96cc-fbb2fda5e6ad
ms.openlocfilehash: c06015ea32bb9f54653e350966bd8089c98628b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135942"
---
# <a name="walkthrough-deploying-a-visual-c-application-to-an-application-local-folder"></a>チュートリアル: アプリケーションのローカル フォルダーへの Visual C++ アプリケーションの配置

ファイルをフォルダーにコピーして、Visual C ++ アプリケーションを配置する方法について説明します。

## <a name="prerequisites"></a>前提条件

- Visual Studio がインストールされているコンピューター。

- Visual C ++ ライブラリがない別のコンピューター。

### <a name="to-deploy-an-application-to-an-application-local-folder"></a>アプリケーションをアプリケーションのローカル フォルダーに配置するには

1. 「[チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置](walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md)」の手順に従って、MFC ++ アプリケーションを作成してビルドします。

1. \\VC\\redist\\*version* フォルダー内の Visual Studio インストール ディレクトリから、適切な MFC および C ランタイム (CRT) ライブラリ ファイルをコピーし、MFC プロジェクトの \Release\ フォルダーに貼り付けます。 場合によってはコピーする必要がある他のファイルの詳細については、「[再配布する DLL の決定](determining-which-dlls-to-redistribute.md)」を参照してください。

1. Visual C ++ ライブラリがない 2 台目のコンピューターで、MFC アプリケーションを実行します。

   1. \Release\ フォルダーの内容をコピーし、2 台目のコンピューター上のアプリケーション フォルダーに貼り付けます。

   1. 2 台目のコンピューターでアプリケーションを実行します。

   Visual C ++ ライブラリはアプリケーションのローカル フォルダーにあるため、アプリケーションは正常に実行されます。

## <a name="see-also"></a>関連項目

[デプロイの例](deployment-examples.md)<br/>
