---
title: MFC インターネット プログラミングの作業 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet applications [MFC], getting started
- Internet applications [MFC], first steps
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df7efbc8d29b2e36c6911255389cc270e7bf5e37
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-internet-programming-tasks"></a>MFC インターネット プログラミングのタスク
このセクションには、アプリケーションにインターネット サポートを追加するための詳細な手順が含まれています。 トピックには、既存の COM コンポーネントをアクティブなドキュメントのサポートを追加する方法と、既存のアプリケーションのインターネット対応にする MFC クラスを使用する方法が含まれます。 最新の株価情報、ピッツバーグの試合の結果を持つドキュメントを作成するし、南極 Microsoft の最新の温度がインターネット経由で行うを支援するテクノロジの数を提供します。  
  
 Active テクノロジには、ActiveX コントロールが含まれます (以前の OLE コントロール) とアクティブなドキュメントです。WinInet を簡単に取得して、インターネットの間でファイルを保存します。および効率的なデータをダウンロードするための非同期モニカーです。 Visual C では、スターター アプリケーションをすばやく開始するのに役立つウィザードが用意されています。 これらのテクノロジの概要については、次を参照してください。 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)と[MFC COM](../mfc/mfc-com.md)です。  
  
 常にファイルを ftp られたりしていない学習済みの WinSock とネットワーク プロトコル WinInet クラスのプログラミングをカプセル化これらのプロトコルでは、ファイルをダウンロードするインターネット上のクライアント アプリケーションの作成に使用できる関数の簡単なセットを提供します。HTTP、FTP、および gopher を使用します。 WinInet を使用すると、ハード ドライブに、世界中のディレクトリを検索します。 透過的にいくつかのさまざまな種類のデータを収集し、統合されたインターフェイスでユーザーに提示できます。  
  
 量が多い場合がある非同期のダウンロードするデータのモニカーはラージ オブジェクトのレンダリングをプログレッシブの COM (コンポーネント オブジェクト モデル) ソリューションを提供します。 Wininet の基礎は非同期的にも使用できます。  
  
 次の表では、これらのテクノロジで実行できる処理の一部について説明します。  
  
|あります。|をします。|行う必要があります。|  
|--------------|-----------------|----------------|  
|Web サーバー。|ログオンおよび URL 要求に関する詳細情報を追跡します。|ログオン イベントと URL マッピングの通知を要求フィルターを作成します。|  
|Web ブラウザー。|動的なコンテンツを提供します。|ActiveX コントロールとアクティブなドキュメントを作成します。|  
|ドキュメント ベースのアプリケーションです。|FTP ファイルにサポートを追加します。|WinInet または非同期モニカーを使用します。|  
  
 作業開始するための詳細については、次のトピックを参照してください。  
  
-   [アプリケーションのデザイン上の検討事項](../mfc/application-design-choices.md)  
  
-   [MFC アプリケーションの作成](../mfc/writing-mfc-applications.md)  
  
-   [インターネット上の ActiveX コントロール](../mfc/activex-controls-on-the-internet.md)  
  
-   [既存の ActiveX コントロールのアップグレード](../mfc/upgrading-an-existing-activex-control.md)  
  
-   [インターネット上の Active ドキュメント](../mfc/active-documents-on-the-internet.md)  
  
-   [インターネット上の非同期モニカー](../mfc/asynchronous-monikers-on-the-internet.md)  
  
-   [インターネット アプリケーションのテスト](../mfc/testing-internet-applications.md)  
  
-   [インターネット セキュリティ](../mfc/internet-security-cpp.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC インターネット プログラミングの基礎](../mfc/mfc-internet-programming-basics.md)   
 [タスク別のインターネット情報](../mfc/internet-information-by-task.md)

