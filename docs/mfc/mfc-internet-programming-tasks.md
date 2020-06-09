---
title: MFC インターネット プログラミングのタスク
ms.date: 09/12/2018
helpviewer_keywords:
- Internet applications [MFC], getting started
- Internet applications [MFC], first steps
ms.assetid: 6377e9b8-07c4-4380-b63b-05f5a9061313
ms.openlocfilehash: 6d8a542ada94bc52ee2000bc92ae0457ec87609c
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617961"
---
# <a name="mfc-internet-programming-tasks"></a>MFC インターネット プログラミングのタスク

ここでは、アプリケーションにインターネットサポートを追加するための詳細な手順について説明します。 MFC クラスを使用して既存のアプリケーションをインターネットで有効にする方法と、既存の COM コンポーネントに Active ドキュメントサポートを追加する方法についても説明します。 ドキュメントの作成には、最大で1分間の株価、ピッツバーグのフットボールスコア、および南極の最新の気温が含まれています。マイクロソフトは、これをインターネット経由で行うためのさまざまなテクノロジを提供しています。

アクティブなテクノロジには、ActiveX コントロール (以前の OLE コントロール) とアクティブなドキュメントが含まれます。インターネット経由で簡単にファイルを取得して保存するための WinInet。データを効率的にダウンロードするための非同期モニカー。 Visual C++ には、スターターアプリケーションをすぐに使い始めるためのウィザードが用意されています。 これらのテクノロジの概要については、「 [Mfc インターネットプログラミングの基礎](mfc-internet-programming-basics.md)」および「 [mfc COM](mfc-com.md)」を参照してください。

ファイルを FTP する必要がありますが、WinSock およびネットワークプログラミングプロトコルを学習していない場合、WinInet クラスはこれらのプロトコルをカプセル化し、HTTP、FTP、gopher を使用してファイルをダウンロードするためのクライアントアプリケーションをインターネット上に作成するために使用できる単純な一連の関数を提供します。 WinInet を使用して、ハードドライブまたは世界中のディレクトリを検索することができます。 さまざまな種類のデータを透過的に収集し、統合されたインターフェイスでユーザーに提示することができます。

大量のデータをダウンロードする非同期モニカーは、ラージオブジェクトのプログレッシブレンダリング用の COM (コンポーネントオブジェクトモデル) ソリューションを提供します。 WinInet は、非同期的に使用することもできます。

次の表では、これらのテクノロジを使用して実行できるいくつかの操作について説明します。

|使用しているユーザー|目的|必要なのは|
|--------------|-----------------|----------------|
|Web サーバー。|ログオンと URL 要求に関する詳細情報を追跡します。|フィルターを記述し、ログオンイベントと URL マッピングの通知を要求します。|
|Web ブラウザー。|動的なコンテンツを提供します。|ActiveX コントロールとアクティブなドキュメントを作成します。|
|ドキュメントベースのアプリケーション。|FTP にサポートを追加します。|WinInet または非同期モニカーを使用します。|

作業を開始するための詳細については、次のトピックを参照してください。

- [アプリケーションのデザイン上の検討事項](application-design-choices.md)

- [MFC アプリケーションの作成](writing-mfc-applications.md)

- [インターネット上の ActiveX コントロール](activex-controls-on-the-internet.md)

- [既存の ActiveX コントロールのアップグレード](upgrading-an-existing-activex-control.md)

- [インターネット上の非同期モニカー](asynchronous-monikers-on-the-internet.md)

- [インターネット アプリケーションのテスト](testing-internet-applications.md)

- [インターネット セキュリティ](internet-security-cpp.md)

## <a name="see-also"></a>関連項目

[MFC インターネットプログラミングの基礎](mfc-internet-programming-basics.md)<br/>
[タスク別のインターネット情報](internet-information-by-task.md)
