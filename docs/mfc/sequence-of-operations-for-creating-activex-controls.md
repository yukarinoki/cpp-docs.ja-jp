---
title: ActiveX コントロールの作成操作のシーケンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
- sequence [MFC], for creating ActiveX controls
- OLE controls [MFC], MFC
- sequence [MFC]
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: caf4c74f2263505ad5d7112021003f92c85a4b84
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380371"
---
# <a name="sequence-of-operations-for-creating-activex-controls"></a>ActiveX コントロールの作成手順
次の表は、ActiveX コントロール (以前の OLE コントロール) を作成して、フレームワークの役割分担を示します。  
  
### <a name="creating-activex-controls"></a>ActiveX コントロールを作成します。  
  
|タスク|そうですよね|フレームワークを動作します。|  
|----------|------------|------------------------|  
|ActiveX コントロール フレームワークを作成します。|コントロールを作成するには、MFC ActiveX コントロール ウィザードを実行します。 [オプション] ページで必要なオプションを指定します。 オプションには、プロジェクト、ライセンス、サブクラス化、およびバージョン情報ボックス メソッドでのコントロールの名前と型が含まれます。|MFC ActiveX コントロール ウィザード、アプリケーション、コントロール、およびプロパティ ページまたはページのソース ファイルを含む、基本的な機能を持つ ActiveX コントロール用のファイルを作成します。リソース ファイルです。プロジェクト ファイルです。仕様に合わせてすべて、他のユーザーです。|  
|独自のコードの行を追加することがなく、コントロールと ActiveX コントロール ウィザードが提供するして参照してください。|ActiveX コントロールをビルドし、Internet Explorer を使用してテストまたは[TSTCON サンプル](../visual-cpp-samples.md)です。|実行中のコントロールは、サイズを変更しても、移動する権限を持ちます。 さらに、**バージョン情報 ボックス**メソッド選択された場合) を呼び出すことができます。|  
|コントロールのメソッドとプロパティを実装します。|コントロールのデータへの公開されているインターフェイスを提供するメンバー関数を追加することで、コントロールに固有のメソッドとプロパティを実装します。 データ構造を保持しを決定するときにイベントを発生させるイベント ハンドラーを使用するメンバー変数を追加します。|フレームワークでは、コントロールのイベント、プロパティ、メソッド、プロパティとメソッドの実装方法に重点を置くことをサポートするためのマップは既に定義します。 既定のプロパティ ページが表示可能なと既定のバージョン情報ボックス メソッドを提供します。|  
|コントロールのプロパティ ページまたはページを構築します。|コントロールのプロパティ ページのインターフェイスを視覚的に編集するのにには、Visual C リソース エディターを使用します。<br /><br /> -追加のプロパティ ページを作成します。<br />-作成し、ビットマップ、アイコン、カーソルを編集します。<br /><br /> ダイアログ エディターで、プロパティ ページをテストすることもできます。|MFC アプリケーション ウィザードによって作成された既定のリソース ファイルは、必要なリソースの多くを提供します。 Visual C では、既存のリソースを編集し、簡単かつ視覚的に、新しいリソースを追加することができます。|  
|コントロールのイベント、メソッド、およびプロパティをテストします。|コントロールを再構築し、テスト コンテナーを使用してハンドラーが正しく動作するをテストします。|コントロールのメソッドを呼び出すし、プロパティ ページのインターフェイス、またはテスト コンテナーを通じてそのプロパティを操作できます。 さらに、コントロールで発生したイベントの追跡とコントロールのコンテナーが受信した通知をテスト コンテナーを使用します。|  
  
## <a name="see-also"></a>関連項目  
 [フレームワークでのビルド](../mfc/building-on-the-framework.md)   
 [MFC アプリケーションの作成操作のシーケンス](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE アプリケーションの作成操作のシーケンス](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [データベース アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-database-applications.md)

