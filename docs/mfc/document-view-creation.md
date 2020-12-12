---
description: '詳細情報: ドキュメント/ビューの作成'
title: Document-View の作成
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
ms.openlocfilehash: 128b68eb53bd596ba2e4b4df4f2c5e865452fe2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326436"
---
# <a name="documentview-creation"></a>ドキュメントおよびビューの作成

フレームワークでは、[**ファイル**] メニューに **新しい** コマンドと **開い** ているコマンド (その他) の実装が用意されています。 新しいドキュメントとそれに関連付けられているビューおよびフレームウィンドウの作成は、アプリケーションオブジェクト、ドキュメントテンプレート、新しく作成されたドキュメント、および新しく作成されたフレームウィンドウの間の共同作業です。 次の表は、どのオブジェクトがどのオブジェクトを作成するかをまとめたものです。

### <a name="object-creators"></a>オブジェクトの作成者

|Creator|作成|
|-------------|-------------|
|アプリケーション オブジェクト|ドキュメントテンプレート|
|ドキュメントテンプレート|ドキュメント|
|ドキュメントテンプレート|フレームウィンドウ|
|フレームウィンドウ|表示|

## <a name="see-also"></a>関連項目

[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメントテンプレートの作成](document-template-creation.md)<br/>
[MFC オブジェクト間の関係](relationships-among-mfc-objects.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](creating-new-documents-windows-and-views.md)
