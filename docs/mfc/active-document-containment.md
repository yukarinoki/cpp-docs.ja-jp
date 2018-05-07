---
title: Active ドキュメント コンテインメント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74ad16aa453c6fa0df2c84bd0a0a789b05f83169
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="active-document-containment"></a>Active ドキュメント コンテインメント
Active ドキュメント コンテインメントは、強制的に作成し、各ドキュメントの種類の複数のアプリケーションのフレームを使用することではなく、ドキュメントを処理するための 1 つのフレームを提供するテクノロジです。 OLE の機能を 1 つのコンテンツのみアクティブにできる複合ドキュメント内の埋め込みオブジェクトとを基本的な OLE 技術とは異なります。 Active ドキュメント コンテインメントは 1 つのフレームのコンテキスト内で、ドキュメント全体 (つまり、アプリケーション全体、関連付けられたメニューのツールバー、およびなどを含む) を有効にします。  
  
 Active ドキュメント コンテインメント テクノロジはもともと Office バインダーを実装する Microsoft Office の開発されました。 ただし、テクノロジは、Office バインダー以外 active ドキュメント コンテナーをサポートするために十分な柔軟性が、Office および Office と互換性のあるアプリケーション以外のサーバーのドキュメントをサポートできます。  
  
 アクティブ ドキュメントをホストするアプリケーションが呼び出される、 [active ドキュメント コンテナー](../mfc/active-document-containers.md)です。 そのようなコンテナーには、Microsoft Office バインダーや Microsoft Internet Explorer があります。  
  
 Active ドキュメント コンテインメントには、一連の拡張機能を OLE ドキュメント、OLE の複合ドキュメント テクノロジー実装が使用されます。 拡張機能は、埋め込み、インプレースで 1 つのコンテンツを埋め込むのではなくドキュメント全体を表すオブジェクトを許可する追加のインターフェイスです。 OLE ドキュメントとは、active ドキュメント コンテインメントは、アクティブなドキュメント、およびアクティブなドキュメント自体のユーザー インターフェイス、および操作の機能を提供するサーバーの表示領域を提供するコンテナーを使用します。  
  
 [Active ドキュメント サーバー](../mfc/active-document-servers.md)自体の各オブジェクトでアクティブにするオブジェクトを許可する拡張機能インターフェイスをサポートしている 1 つまたは複数の active ドキュメント クラスをサポートするアプリケーション (Word、Excel、PowerPoint など) には、適切なコンテナーです。  
  
 [アクティブなドキュメント](../mfc/active-documents.md)(Word や Excel などの active ドキュメント サーバーから提供される) 本質的に本格的なコンベンショナル ドキュメント別の active ドキュメント コンテナー内のオブジェクトとして埋め込まれています。 埋め込みオブジェクトとは異なりアクティブ ドキュメントのページを完全に制御を持ち、(アプリケーションのすべての基になるコマンドおよびツール) 完全インターフェイスを使用し、編集するユーザーを。  
  
 アクティブなドキュメントは、標準の OLE 埋め込みオブジェクトから区別することによって良く理解します。 OLE 規約では、所有されている、ドキュメントのページ内に表示される埋め込みオブジェクトし、OLE コンテナーが、ドキュメントを管理します。 コンテナーは、ドキュメントの残りの部分と埋め込みオブジェクトのデータを格納します。 ただし、埋め込みオブジェクトは、表示されるページを制御しない点で制限されます。  
  
 Active ドキュメント コンテナー アプリケーションのドキュメントを作成できます active (Office バインダーのセクションと呼ばれます) を使用して、お気に入りのアプリケーション (これらのアプリケーションは、アクティブなドキュメントが有効になっている)、まだユーザーとして作成されたプロジェクトを管理できます、一意に名前を指定できます、保存、印刷時に、1 つのエンティティとなどです。 、同じ方法で、インターネット ブラウザーのユーザーが、ネットワーク全体だけでなく、ローカル ファイル システムを 1 つの場所からその記憶域内のドキュメントを参照する機能を 1 つのドキュメントの記憶域エンティティとして扱うことができます。  
  
## <a name="sample-programs"></a>サンプル プログラム  
  
-   [MFCBIND](../visual-cpp-samples.md)サンプル active ドキュメント コンテナー アプリケーションの実装を示しています。  
  
## <a name="see-also"></a>関連項目  
 [MFC COM](../mfc/mfc-com.md)

