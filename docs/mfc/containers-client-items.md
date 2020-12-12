---
description: '詳細については、「コンテナー: クライアントアイテム」を参照してください。'
title: 'コンテナー : クライアント アイテム'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client items
- client items and OLE containers
ms.assetid: 231528b5-0744-4f83-8897-083bf55ed087
ms.openlocfilehash: e8aff84e825723b1615a0dbbadf7d5fec6d4cef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310435"
---
# <a name="containers-client-items"></a>コンテナー : クライアント アイテム

この記事では、クライアント項目の概要と、アプリケーションがクライアント項目を派生させる必要があるクラスについて説明します。

クライアント項目は、OLE コンテナーアプリケーションのドキュメントに含まれているか、または参照されている別のアプリケーションに属するデータ項目です。 データがドキュメント内に含まれているクライアント項目は埋め込まれます。コンテナードキュメントによって参照される別の場所にデータが格納されているデータがリンクされています。

OLE アプリケーションのドキュメントクラスは、からではなく、 [COleDocument](reference/coledocument-class.md) クラスから派生し `CDocument` ます。 クラスは、 `COleDocument` `CDocument` MFC アプリケーションの基になるドキュメント/ビューアーキテクチャを使用するために必要なすべての機能を継承します。 `COleDocument` は、ドキュメントをオブジェクトのコレクションとして扱うインターフェイスも定義し `CDocItem` ます。 `COleDocument`コレクションの要素を追加、取得、および削除するために、いくつかのメンバー関数が用意されています。

すべてのコンテナーアプリケーションは、から少なくとも1つのクラスを派生させる必要があり `COleClientItem` ます。 このクラスのオブジェクトは、OLE ドキュメント内の埋め込みまたはリンクされた項目を表します。 これらのオブジェクトは、ドキュメントから削除されていない限り、ドキュメントが含まれているドキュメントの有効期間にわたって存在します。

`CDocItem` は、およびの基本クラスです `COleClientItem` `COleServerItem` 。 これら2つから派生したクラスのオブジェクトは、それぞれ OLE 項目とクライアントアプリケーションとサーバーアプリケーションの間の仲介役として機能します。 新しい OLE 項目がドキュメントに追加されるたびに、MFC フレームワークによって、クライアントアプリケーションの派生クラスの新しいオブジェクトが `COleClientItem` ドキュメントのオブジェクトのコレクションに追加され `CDocItem` ます。

## <a name="see-also"></a>関連項目

[Containers](containers.md)<br/>
[コンテナー: 複合ファイル](containers-compound-files.md)<br/>
[コンテナー: User-Interface の問題](containers-user-interface-issues.md)<br/>
[コンテナー: 高度な機能](containers-advanced-features.md)<br/>
[COleClientItem クラス](reference/coleclientitem-class.md)<br/>
[COleServerItem クラス](reference/coleserveritem-class.md)
