---
description: '詳細情報: ドキュメント/ビューアーキテクチャ'
title: Document-View アーキテクチャ
ms.date: 11/19/2018
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
ms.openlocfilehash: ef6746a77a3f8a482c347d61685fccad3e6b4dfb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339723"
---
# <a name="documentview-architecture"></a>ドキュメント/ビュー アーキテクチャ

既定では、MFC アプリケーションウィザードは、ドキュメントクラスとビュークラスを使用してアプリケーションスケルトンを作成します。 MFC では、データ管理をこの2つのクラスに分割します。 このドキュメントでは、データを格納し、データの印刷を管理し、データの複数のビューの更新を調整します。 ビューには、データが表示され、選択や編集など、データとのユーザー操作を管理します。

このモデルでは、MFC ドキュメントオブジェクトが永続ストレージに対してデータの読み取りと書き込みを行います。 ドキュメントには、データが置かれている場所 (データベースなど) へのインターフェイスも用意されている場合があります。 独立したビューオブジェクトは、ウィンドウのデータをユーザーが選択して編集するためのデータ表示を管理します。 ビューでは、ドキュメントから表示データが取得され、データが変更されるとドキュメントに返信されます。

ドキュメント/ビューの分離を簡単にオーバーライドまたは無視できますが、ほとんどの場合、このモデルに従うことが非常に重要な理由があります。 最適な方法の1つは、スプレッドシートとグラフビューの両方など、同じドキュメントの複数のビューが必要な場合です。 ドキュメント/ビューモデルでは、データの各ビューを個別のビューオブジェクトで表すことができます。一方、すべてのビュー (計算エンジンなど) に共通するコードは、ドキュメントに含めることができます。 このドキュメントでは、データが変更されるたびにすべてのビューを更新するタスクについても説明します。

MFC のドキュメント/ビューアーキテクチャを使用すると、複数のビュー、複数のドキュメントの種類、分割ウィンドウ、およびその他の重要なユーザーインターフェイス機能を簡単にサポートできます。

ユーザーとプログラマの両方にとって最もわかりやすい MFC フレームワークの部分は、ドキュメントとビューです。 フレームワークを使用したアプリケーション開発の作業のほとんどは、ドキュメントを作成し、クラスを表示します。 この記事ファミリでは次のことについて説明します。

- ドキュメントとビューの目的、およびフレームワーク内でのそれらの対話方法。

- それらを実装するために行う必要があること。

ドキュメント/ビューの中核となるのは、次の4つの主要なクラスです。

[CDocument](reference/cdocument-class.md) (または[COleDocument](reference/coledocument-class.md)) クラスは、プログラムのデータの格納や制御に使用されるオブジェクトをサポートし、プログラマが定義したドキュメントクラスの基本機能を提供します。 ドキュメントは、通常、[ファイル] メニューの [開く] コマンドを使用してユーザーが開くデータの単位を表し、[ファイル] メニューの [保存] コマンドを使用して保存します。

[CView](reference/cview-class.md) (またはその多くの派生クラスの1つ) には、プログラマが定義したビュークラスの基本機能が用意されています。 ビューはドキュメントにアタッチされ、ドキュメントとユーザーの間の仲介役として機能します。このビューは、ドキュメントの画像を画面に表示し、ユーザーの入力をドキュメントに対する操作として解釈します。 また、このビューでは、印刷と印刷プレビューの両方のイメージがレンダリングされます。

[CFrameWnd](reference/cframewnd-class.md) (またはそのバリエーションの1つ) では、ドキュメントの1つ以上のビューの周囲にフレームを提供するオブジェクトがサポートされています。

[CDocTemplate](reference/cdoctemplate-class.md) (または [CSingleDocTemplate](reference/csingledoctemplate-class.md) または [CMultiDocTemplate](reference/cmultidoctemplate-class.md)) は、指定された種類の1つ以上の既存のドキュメントを調整し、その型の正しいドキュメント、ビュー、およびフレームウィンドウオブジェクトの作成を管理するオブジェクトをサポートします。

次の図は、ドキュメントとそのビューの関係を示しています。

![ビューは表示されているドキュメントの一部です](../mfc/media/vc379n1.gif "ビューは表示されているドキュメントの一部です") <br/>
ドキュメントとビュー

クラスライブラリのドキュメント/ビュー実装は、データ自体をその表示とユーザー操作から分離します。 データへのすべての変更は、ドキュメントクラスによって管理されます。 ビューは、このインターフェイスを呼び出してデータにアクセスし、データを更新します。

ドキュメント、関連付けられたビュー、およびビューをフレーム化するフレームウィンドウは、ドキュメントテンプレートによって作成されます。 ドキュメントテンプレートは、1つのドキュメントの種類のすべてのドキュメントを作成および管理する役割を担います。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ドキュメント/ビューアーキテクチャの全体像](a-portrait-of-the-document-view-architecture.md)

- [ドキュメント/ビューアーキテクチャの利点](advantages-of-the-document-view-architecture.md)

- [アプリケーションウィザードによって作成されるドキュメントクラスとビュークラス](document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [ドキュメント/ビューアーキテクチャの代替手段](alternatives-to-the-document-view-architecture.md)

- [1つのドキュメントに複数のビューを追加する](adding-multiple-views-to-a-single-document.md)

- [ドキュメントの使用](using-documents.md)

- [ビューの使用](using-views.md)

- [複数のドキュメントタイプ、ビュー、フレームウィンドウ](multiple-document-types-views-and-frame-windows.md)

- [ドキュメントとビューの初期化と後処理](initializing-and-cleaning-up-documents-and-views.md)

- [ドキュメント & ビュークラスに対する独自の追加の初期化](creating-new-documents-windows-and-views.md)

- [ドキュメントとビューを用いたデータベース クラスの使用](../data/mfc-using-database-classes-with-documents-and-views.md)

- [ドキュメントとビューを用いないデータベース クラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)

- [サンプル](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>関連項目

[ユーザーインターフェイス要素](user-interface-elements-mfc.md)<br/>
[Windows](windows.md)<br/>
[フレームウィンドウ](frame-windows.md)<br/>
[ドキュメントテンプレートとドキュメント/ビュー作成プロセス](document-templates-and-the-document-view-creation-process.md)<br/>
[ドキュメント/ビューの作成](document-view-creation.md)<br/>
[新しいドキュメント、ウィンドウ、およびビューの作成](creating-new-documents-windows-and-views.md)
