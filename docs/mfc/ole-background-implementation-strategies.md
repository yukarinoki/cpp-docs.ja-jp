---
title: 'OLE の背景知識: 実装戦略 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE [MFC], development strategy
- OLE applications [MFC], implementing OLE
- applications [OLE], implementing OLE
ms.assetid: 0875ddae-99df-488c-82c6-164074a81058
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe15690b50c9398d660ca53effbec23cc35f49e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-background-implementation-strategies"></a>OLE の背景知識 : 実装の方法
アプリケーションによっては、OLE サポートを追加するための 4 つの可能な実装戦略があります。  
  
-   新しいアプリケーションを作成しています。  
  
     このような状況は、最も少ない通常必要があります。 作業します。 MFC アプリケーション ウィザードを実行し、型、または高度な機能、スケルトン アプリケーションを作成する複合ドキュメント サポートを選択するとします。 これらのオプションとその実行内容については、記事を参照してください。 [MFC EXE プログラムを作成する](../mfc/reference/mfc-application-wizard.md)です。  
  
-   OLE をサポートしていない Microsoft Foundation Class ライブラリ バージョン 2.0 以降で記述されたプログラムがあります。  
  
     既に触れましたが、MFC アプリケーション ウィザードを使用して、新しいアプリケーションを作成し、コピーして、既存のアプリケーションに新しいアプリケーションのコードを貼り付けます。 これは、サーバー、コンテナー、または自動アプリケーションの機能です。 MFC を参照してください[SCRIBBLE](../visual-cpp-samples.md)この方法の例のサンプルです。  
  
-   OLE バージョン 1.0 のサポートを実装している Microsoft Foundation Class ライブラリ プログラムがあります。  
  
     参照してください[MFC テクニカル ノート 41](../mfc/tn041-mfc-ole1-migration-to-mfc-ole-2.md)この変換方法を使用します。  
  
-   Microsoft Foundation Classes を使用して書き込んだではありませんをするか、および OLE サポート実装されていませんが、アプリケーションがあります。  
  
     このような状況では、最も多くの作業が必要です。 1 つの方法では、最初の方法と同様に、新しいアプリケーションを作成し、コピーして、既存のコードを貼り付けます。 場合は、既存のコードは、C で記述された、C コードとしてコンパイルできるように変更する必要があります。 場合は、C コードでは、Windows API を呼び出す、Microsoft Foundation classes を使用するように変更する必要はありません。 多くの場合は、Microsoft Foundation Classes の 2.0 以降のバージョンで使用される、ドキュメント/ビュー アーキテクチャをサポートするために、プログラムのいくつかの制限が必要です。 このアーキテクチャの詳細については、次を参照してください。[テクニカル ノート 25](../mfc/tn025-document-view-and-frame-creation.md)です。  
  
 読み取りを行ってください戦略を決定した後、[コンテナー](../mfc/containers.md)または[サーバー](../mfc/servers.md)記事の種類に応じて作成するアプリケーションの) またはサンプル プログラムまたはその両方を確認します。 MFC OLE サンプル[OCLIENT](../visual-cpp-samples.md)と[HIERSVR](../visual-cpp-samples.md)コンテナーと、サーバーのさまざまな側面をそれぞれ実装方法について説明します。 これらの記事全体でさまざまな時点で説明されている手法の例として、これらのサンプルでの特定の関数に呼ばれます。  
  
## <a name="see-also"></a>関連項目  
 [OLE の背景知識](../mfc/ole-background.md)   
 [コンテナー: コンテナーの実装](../mfc/containers-implementing-a-container.md)   
 [サーバー: サーバーの実装](../mfc/servers-implementing-a-server.md)   
 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)

