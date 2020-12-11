---
description: '詳細情報: ドキュメントデータ変数を使用したデータの管理'
title: ドキュメント データ変数を使ったデータ管理
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], data storage
- friend classes [MFC]
- classes [MFC], friend
- data [MFC]
- data [MFC], documents
- collection classes [MFC], used by document object
- document data [MFC]
- member variables [MFC], document class [MFC]
ms.assetid: e70b87f4-8c30-49e5-8986-521c2ff91704
ms.openlocfilehash: d05bfe71d080c08b3e0f3bbd416421e612b5d7ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112207"
---
# <a name="managing-data-with-document-data-variables"></a>ドキュメント データ変数を使ったデータ管理

ドキュメントクラスのメンバー変数として、ドキュメントのデータを実装します。 たとえば、Scribble プログラムは、 `CObList` オブジェクトへのポインターを格納するリンクリストである型のデータメンバーを宣言し `CObject` ます。 このリストは、フリーハンドの線描画を構成するポイントの配列を格納するために使用されます。

ドキュメントのメンバーデータをどのように実装するかは、アプリケーションの性質によって異なります。 これを実現するために、MFC では、、、、、などのさまざまな共通データ型をカプセル化するクラスと共に、"コレクションクラス" (C++ テンプレートに基づくコレクションを含む) のグループを提供して `CString` `CRect` `CPoint` `CSize` `CTime` います。 これらのクラスの詳細については、「 *MFC リファレンス*」の「[クラスライブラリの概要](class-library-overview.md)」を参照してください。

ドキュメントのメンバーデータを定義する場合、通常は、ドキュメントクラスにメンバー関数を追加して、データ項目を設定および取得し、その他の便利な操作を実行します。

ビューは、作成時にビューにインストールされたドキュメントへのビューのポインターを使用して、ドキュメントオブジェクトにアクセスします。 メンバー関数を呼び出すことにより、ビューのメンバー関数でこのポインターを取得でき `CView` `GetDocument` ます。 このポインターは、必ず独自のドキュメント型にキャストしてください。 その後、ポインターを使用してパブリックドキュメントのメンバーにアクセスできます。

頻繁なデータ転送に直接アクセスが必要な場合、またはドキュメントクラスの非パブリックメンバーを使用する場合は、ビュークラスをドキュメントクラスのフレンド (C++ 用語) にすることができます。

## <a name="see-also"></a>関連項目

[ドキュメントの使用](using-documents.md)
