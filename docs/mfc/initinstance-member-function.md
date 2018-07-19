---
title: InitInstance メンバー関数は、|Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- InitInstance
dev_langs:
- C++
helpviewer_keywords:
- InitInstance method [MFC]
- applications [MFC], initializing
- MFC, initializing
- initializing MFC applications
ms.assetid: 4ef09267-ff7f-4c39-91a0-57454a264f83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9379fef6a1d676d6a3bc757ee51d5d27acd5f6f
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930177"
---
# <a name="initinstance-member-function"></a>InitInstance メンバー関数
Windows オペレーティング システムでは、複数のコピー、または「インスタンス」の同じアプリケーションを実行することができます。 `WinMain` 呼び出し[InitInstance](../mfc/reference/cwinapp-class.md#initinstance)アプリケーションの新しいインスタンスを起動するたびにします。  
  
 標準`InitInstance`MFC アプリケーション ウィザードによって作成された実装は、次のタスクを実行します。  
  
-   中央のアクションとして、ドキュメント、ビュー、およびフレーム ウィンドウを作成するドキュメント テンプレートを作成します。 このプロセスの説明は、次を参照してください。[ドキュメント テンプレートの作成](../mfc/document-template-creation.md)です。  
  
-   .Ini ファイルや、最近使用したファイルの名前を含む、Windows レジストリから標準のファイル オプションを読み込みます。  
  
-   1 つまたは複数のドキュメント テンプレートを登録します。  
  
-   MDI アプリケーションは、メイン フレーム ウィンドウを作成します。  
  
-   コマンドラインをコマンドラインで指定されたドキュメントを開くかを開くには新しい空のドキュメントを処理します。  
  
 独自の初期化コードを追加したり、ウィザードによって作成されたコードを変更することができます。  
  
> [!NOTE]
>  MFC アプリケーションは、シングルスレッド アパートメント (STA) として初期化する必要があります。 呼び出す場合[CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)で、`InitInstance`上書き、COINIT_APARTMENTTHREADED (COINIT_MULTITHREADED ではなく) を指定します。 詳細については、[prb] を参照してください: MFC アプリケーションとして、マルチ スレッド アパートメント (828643) でアプリケーションを初期化するときの応答を停止[ http://support.microsoft.com/default.aspxscid=kb; en-us; 828643](http://support.microsoft.com/default.aspxscid=kb;en-us;828643)です。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
