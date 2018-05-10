---
title: 'Active ドキュメント コンテインメントの例: Office バインダー |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7e4f82840a4c5620762ad57b5b9fa8dd7e62d0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="example-of-active-document-containment-office-binder"></a>Active ドキュメント コンテインメントの例 : Office バインダー
Microsoft Office バインダーは、active ドキュメント コンテナーの例を示します。 Office バインダーには、コンテナーと同様の 2 つのプライマリ ペインが含まれています。 左側のウィンドウには、バインダー内のアクティブなドキュメントに対応するアイコンが含まれています。 各ドキュメントと呼ばれる、*セクション*バインダー内です。 たとえば、バインダーは、Word 文書、PowerPoint ファイル、Excel スプレッドシート、およびなどを含めることができます。  
  
 左側のウィンドウでアイコンをクリックすると、対応するアクティブなドキュメントがアクティブにします。 バインダーの右側のウィンドウは、現在選択されているアクティブなドキュメントの内容を表示します。  
  
 開いてバインダーで Word 文書をアクティブ化すると、ビュー フレームの上部にある単語のメニュー バーとツールバーが表示され、Word コマンドまたはツールを使用して、ドキュメントの内容を編集することができます。 ただし、メニュー バーは、バインダーと Word の両方のメニュー バーの組み合わせです。 バインダーと Word の両方であるため**ヘルプ**メニュー、各メニューの内容がマージされます。 Office バインダーなどの active ドキュメント コンテナーが自動的に提供**ヘルプ** メニューのマージ; 詳細についてを参照してください[ヘルプ メニューのマージ](../mfc/help-menu-merging.md)です。  
  
 別のアプリケーションの種類、バインダーのインターフェイスの変更に、アクティブなドキュメントのアプリケーションの種類の対応するための作業中のドキュメントを選択するとします。 たとえば、バインダー Excel スプレッドシートが含まれている場合、Excel スプレッドシートのセクションを選択すると、バインダーのメニューを変更することを観察はします。  
  
 もちろん、バインダーの横にあるコンテナーの考えられる他の種類があります。 ファイル エクスプ ローラーでは、左側のウィンドウが右側のペインでは、現在選択されているディレクトリに含まれているファイルを表示中に、ドライブまたはネットワーク ディレクトリの階層リストを表示するツリーのコントロールを使用する一般的なデュアル ウィンドウのインターフェイスを使用します。 デュアル ウィンドウ インターフェイスを使用するのではなく、コンテナー (Microsoft Internet Explorer など) のインターネット ブラウザーの種類は通常 1 つのフレームがあり、ハイパーリンクを使用して移動できるようにします。  
  
## <a name="see-also"></a>関連項目  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

