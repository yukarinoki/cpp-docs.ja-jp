---
title: シングル ドキュメントへのマルチ ビューの追加
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 4fa39a4d9369c84d2cffdaeff28dc9cb2f966b31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370864"
---
# <a name="adding-multiple-views-to-a-single-document"></a>シングル ドキュメントへのマルチ ビューの追加

MFC (MFC) ライブラリで作成されたシングル ドキュメント インターフェイス (SDI) アプリケーションでは、各ドキュメントの種類は、1 つのビューの種類に関連付けられます。 場合によっては、ドキュメントの現在のビューを新しいビューに切り替える機能が必要です。

> [!TIP]
> 1 つのドキュメントに複数のビューを実装する手順の詳細については[、「CDocument::AddView」](../mfc/reference/cdocument-class.md#addview)および「[コレクション](../overview/visual-cpp-samples.md)MFC サンプル」を参照してください。

この機能を実装するには、新しい`CView`派生クラスと、ビューを既存の MFC アプリケーションに動的に切り替えるコードを追加します。

手順は次のとおりです。

- [既存のアプリケーション クラスを変更する](#vcconmodifyexistingapplicationa1)

- [新しいビュー クラスの作成と変更](#vcconnewviewclassa2)

- [新しいビューを作成してアタッチする](#vcconattachnewviewa3)

- [スイッチング機能の実装](#vcconswitchingfunctiona4)

- [ビューの切り替えのサポートを追加する](#vcconswitchingtheviewa5)

このトピックの残りの部分では、次の事項を前提としています。

- 派生オブジェクトの`CWinApp`名前は`CMyWinApp``CMyWinApp`*、MYWINAPP で宣言および定義されます。H*と*マイウィナップ。CPP*.

- `CNewView`は、新しい`CView`派生オブジェクトの名前であり`CNewView`*、NEWVIEW で宣言および定義されます。H*と*ニュービュー。CPP*.

## <a name="modify-the-existing-application-class"></a><a name="vcconmodifyexistingapplicationa1"></a>既存のアプリケーション クラスを変更する

アプリケーションでビューを切り替えるには、ビューを格納するメンバー変数と、ビューを切り替えるメソッドを追加して、アプリケーション クラスを変更する必要があります。

MYWINAPP の宣言に次`CMyWinApp`のコードを追加*します。H*:

[!code-cpp[NVC_MFCDocViewSDI#1](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

新しいメンバー変数、 `m_pOldView` `m_pNewView`と を指定すると、現在のビューと新しく作成されたビューを指します。 新しいメソッド`SwitchView`( ) は、ユーザーから要求された場合にビューを切り替えます。 メソッドの本文については、このトピックの後半の「[スイッチング機能の実装](#vcconswitchingfunctiona4)」で説明します。

アプリケーション クラスの最後の変更には、切り替え関数で使用される Windows メッセージ (**WM_INITIALUPDATE**) を定義する新しいヘッダー ファイルが含まれている必要があります。

MYWINAPP のインクルード セクションに次の行を挿入*します。CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

変更を保存して、次の手順に進みます。

## <a name="create-and-modify-the-new-view-class"></a><a name="vcconnewviewclassa2"></a>新しいビュー クラスの作成と変更

新しいビュー クラスの作成は、[クラス ビュー] から [**新しいクラス**] コマンドを使用して簡単に作成できます。 このクラスの唯一の要件は、 から`CView`派生することです。 この新しいクラスをアプリケーションに追加します。 プロジェクトへの新しいクラスの追加の詳細については、「[クラスの追加](../ide/adding-a-class-visual-cpp.md)」を参照してください。

クラスをプロジェクトに追加したら、一部のビュー クラス メンバーのアクセシビリティを変更する必要があります。

*新規ビューを変更します。H*アクセス指定子をコンストラクターおよびデストラクターの**保護**から**パブリック**に変更します。 これにより、クラスを動的に作成および破棄し、表示する前にビューの外観を変更できます。

変更を保存して、次の手順に進みます。

## <a name="create-and-attach-the-new-view"></a><a name="vcconattachnewviewa3"></a>新しいビューを作成してアタッチする

新しいビューを作成してアタッチするには、アプリケーション クラスの`InitInstance`機能を変更する必要があります。 この変更により、新しいビュー オブジェクトを作成し、2 つの`m_pOldView`既存`m_pNewView`のビュー オブジェクトを使用して初期化する新しいコードが追加されます。

新しいビューは関数内で`InitInstance`作成されるため、新しいビューと既存のビューの両方がアプリケーションの有効期間中も保持されます。 ただし、アプリケーションは、新しいビューを動的に作成するのと同じように簡単にできます。

への呼び出しの後`ProcessShellCommand`にこのコードを挿入します。

[!code-cpp[NVC_MFCDocViewSDI#3](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

変更を保存して、次の手順に進みます。

## <a name="implement-the-switching-function"></a><a name="vcconswitchingfunctiona4"></a>スイッチング機能の実装

前の手順では、新しいビュー オブジェクトを作成して初期化するコードを追加しました。 最後の主要な部分は、`SwitchView`スイッチング方法を実装することです。

アプリケーション クラスの実装ファイルの最後に *、MYWINAPP.CPP)* を追加し、次のメソッド定義を追加します。

[!code-cpp[NVC_MFCDocViewSDI#4](../mfc/codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

変更を保存して、次の手順に進みます。

## <a name="add-support-for-switching-the-view"></a><a name="vcconswitchingtheviewa5"></a>ビューの切り替えのサポートを追加する

最後の手順では、アプリケーションがビューを`SwitchView`切り替える必要があるときにメソッドを呼び出すコードを追加します。 これは、いくつかの方法で行うことができます:特定の条件が満たされたときに、ユーザーが選択するための新しいメニュー項目を追加するか、またはビューを内部的に切り替えます。

新しいメニュー項目とコマンド ハンドラー関数の追加の詳細については、「[コマンドとコントロールの通知のハンドラー](../mfc/handlers-for-commands-and-control-notifications.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)
