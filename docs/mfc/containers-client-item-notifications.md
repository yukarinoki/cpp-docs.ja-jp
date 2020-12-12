---
description: '詳細については、「コンテナー: Client-Item 通知」を参照してください。'
title: 'コンテナー : クライアント アイテムへの通知'
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
ms.openlocfilehash: 2918ea29bcd656e76735db8e003d33dce21c6b63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310474"
---
# <a name="containers-client-item-notifications"></a>コンテナー : クライアント アイテムへの通知

この記事では、サーバーアプリケーションがクライアントアプリケーションのドキュメント内の項目を変更するときに、MFC フレームワークが呼び出すオーバーライド可能な関数について説明します。

[COleClientItem](reference/coleclientitem-class.md) は、コンポーネントアプリケーションからの要求への応答として呼び出されるいくつかのオーバーライド可能な関数を定義します。これは、サーバーアプリケーションとも呼ばれます。 これらの overridables は通常、通知として機能します。 これらは、スクロール、アクティブ化、または位置の変更などのさまざまなイベントをコンテナーアプリケーションに通知し、ユーザーが項目を編集または操作するときに加えられた変更を通知します。

フレームワークは、の呼び出しを通じてコンテナーの変更をコンテナーに通知し `COleClientItem::OnChange` ます。これは、実装が必要なオーバーライド可能な関数です。 このプロテクト関数は、2つの引数を受け取ります。 最初のは、サーバーが項目を変更した理由を指定します。

|Notification|説明|
|------------------|-------------|
|**OLE_CHANGED**|OLE 項目の外観が変更されました。|
|**OLE_SAVED**|OLE 項目が保存されました。|
|**OLE_CLOSED**|OLE 項目が閉じられました。|
|**OLE_RENAMED**|OLE 項目を含むサーバードキュメントの名前が変更されました。|
|**OLE_CHANGED_STATE**|OLE 項目がある状態から別の状態に変更されました。|
|**OLE_CHANGED_ASPECT**|OLE 項目の描画の側面は、フレームワークによって変更されています。|

これらの値は、AFXOLE で定義されている **OLE_NOTIFICATION** 列挙体からのものです。

この関数の2番目の引数は、項目がどのように変更されたか、またどの状態が入力されたかを指定します。

|最初の引数が|2 番目の引数|
|----------------------------|---------------------|
|**OLE_SAVED** または **OLE_CLOSED**|は使用されません。|
|**OLE_CHANGED**|変更された OLE 項目の側面を指定します。|
|**OLE_CHANGED_STATE**|入力される状態 (*Emptystate*、読み込まれた *状態*、 *openstate*、 *activeState*、または *activeuistate*) について説明します。|

クライアント項目が想定できる状態の詳細については、「 [コンテナー: Client-Item の状態](containers-client-item-states.md)」を参照してください。

フレームワークは、 `COleClientItem::OnGetItemPosition` 項目が埋め込み先編集のためにアクティブ化されるときにを呼び出します。 インプレース編集をサポートするアプリケーションでは、の実装が必要です。 MFC アプリケーションウィザードには、の `CRect` 引数として渡されるオブジェクトに項目の座標を割り当てる基本的な実装が用意されて `OnGetItemPosition` います。

埋め込み先編集中に OLE 項目の位置またはサイズが変更された場合は、項目の位置とクリッピング四角形に関するコンテナーの情報を更新し、サーバーが変更に関する情報を受け取る必要があります。 フレームワークは、 `COleClientItem::OnChangeItemPosition` この目的のためにを呼び出します。 MFC アプリケーションウィザードには、基底クラスの関数を呼び出すオーバーライドが用意されています。 `COleClientItem`クライアント項目オブジェクトによって保持されている情報が関数によって更新されるように、から派生したクラスに対してアプリケーションウィザードによって書き込まれる関数を編集する必要があります。

## <a name="see-also"></a>関連項目

[Containers](containers.md)<br/>
[コンテナー: Client-Item の状態](containers-client-item-states.md)<br/>
[COleClientItem:: OnChangeItemPosition](reference/coleclientitem-class.md#onchangeitemposition)
