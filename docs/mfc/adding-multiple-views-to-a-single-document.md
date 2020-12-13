---
description: '詳細情報: 1 つのドキュメントに複数のビューを追加する'
title: シングル ドキュメントへのマルチ ビューの追加
ms.date: 11/04/2016
helpviewer_keywords:
- multiple views [MFC], SDI applications
- documents [MFC], multiple views
- single document interface (SDI), adding views
- views [MFC], SDI applications
ms.assetid: 86d0c134-01d5-429c-b672-36cfb956dc01
ms.openlocfilehash: 84f50ad96e4c5939c7ee2e97f8babfaa5221b6f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343732"
---
# <a name="adding-multiple-views-to-a-single-document"></a>シングル ドキュメントへのマルチ ビューの追加

MFC (Microsoft Foundation Class) ライブラリを使用して作成されたシングルドキュメントインターフェイス (SDI) アプリケーションでは、各ドキュメントの種類が1つのビューの種類に関連付けられます。 場合によっては、ドキュメントの現在のビューを新しいビューに切り替える機能があることが望ましい場合があります。

> [!TIP]
> 1つのドキュメントに対して複数のビューを実装する手順の詳細については、「 [CDocument:: AddView](reference/cdocument-class.md#addview) 」と「 [COLLECT](../overview/visual-cpp-samples.md) MFC サンプル」を参照してください。

この機能を実装するには、新しい `CView` 派生クラスを追加し、既存の MFC アプリケーションにビューを動的に切り替えるためのコードを追加します。

手順は次のとおりです。

- [既存のアプリケーションクラスを変更する](#vcconmodifyexistingapplicationa1)

- [新しいビュークラスを作成および変更する](#vcconnewviewclassa2)

- [新しいビューを作成してアタッチする](#vcconattachnewviewa3)

- [切り替え関数を実装する](#vcconswitchingfunctiona4)

- [ビューを切り替えるためのサポートを追加する](#vcconswitchingtheviewa5)

このトピックの残りの部分では、次のことを前提としています。

- 派生オブジェクトの名前 `CWinApp` はであり、 `CMyWinApp` `CMyWinApp` mywinapp で宣言および定義されてい *ます。H* と *Mywinapp。CPP*。

- `CNewView` は、新しい派生オブジェクトの名前です `CView` 。は、 `CNewView` newview で宣言および定義されてい *ます。H* と *newview。CPP*。

## <a name="modify-the-existing-application-class"></a><a name="vcconmodifyexistingapplicationa1"></a> 既存のアプリケーションクラスを変更する

アプリケーションでビューを切り替えるには、ビューを格納するメンバー変数を追加し、それらを切り替えるためのメソッドを追加して、アプリケーションクラスを変更する必要があります。

次のコードを Mywinapp のの宣言に追加 `CMyWinApp` *します。H*:

[!code-cpp[NVC_MFCDocViewSDI#1](codesnippet/cpp/adding-multiple-views-to-a-single-document_1.h)]

新しいメンバー変数である `m_pOldView` とは、 `m_pNewView` 現在のビューと新しく作成されたものを指します。 新しいメソッド () は、 `SwitchView` ユーザーが要求したときにビューを切り替えます。 メソッドの本体については、このトピックで後述する「 [スイッチ関数の実装](#vcconswitchingfunctiona4)」を参照してください。

アプリケーションクラスを最後に変更するには、スイッチ関数で使用される Windows メッセージ (**WM_INITIALUPDATE**) を定義する新しいヘッダーファイルを含める必要があります。

Mywinapp の include セクションに次の行を挿入 *します。CPP*:

[!code-cpp[NVC_MFCDocViewSDI#2](codesnippet/cpp/adding-multiple-views-to-a-single-document_2.cpp)]

変更内容を保存し、次の手順に進みます。

## <a name="create-and-modify-the-new-view-class"></a><a name="vcconnewviewclassa2"></a> 新しいビュークラスを作成および変更する

新しいビュークラスの作成は、クラスビューから利用できる **新しいクラス** コマンドを使用して簡単に行うことができます。 このクラスの唯一の要件は、から派生することです `CView` 。 この新しいクラスをアプリケーションに追加します。 新しいクラスをプロジェクトに追加する方法の詳細については、「 [クラスの追加](../ide/adding-a-class-visual-cpp.md)」を参照してください。

クラスをプロジェクトに追加したら、一部のビュークラスメンバーのアクセシビリティを変更する必要があります。

*Newview を変更します。* **`protected`** 、コンストラクターとデストラクターのアクセス指定子をからに変更し **`public`** ます。 これにより、クラスを動的に作成および破棄し、表示される前に外観を変更することができます。

変更内容を保存し、次の手順に進みます。

## <a name="create-and-attach-the-new-view"></a><a name="vcconattachnewviewa3"></a> 新しいビューを作成してアタッチする

新しいビューを作成してアタッチするには、アプリケーションクラスの関数を変更する必要があり `InitInstance` ます。 この変更により、新しいビューオブジェクトを作成し、 `m_pOldView` `m_pNewView` 2 つの既存のビューオブジェクトを使用してとの両方を初期化する新しいコードが追加されます。

新しいビューは関数内に作成されるため `InitInstance` 、アプリケーションの有効期間中は新しいビューと既存のビューの両方が保持されます。 ただし、アプリケーションでは、新しいビューを動的に簡単に作成できます。

の呼び出しの後に、次のコードを挿入し `ProcessShellCommand` ます。

[!code-cpp[NVC_MFCDocViewSDI#3](codesnippet/cpp/adding-multiple-views-to-a-single-document_3.cpp)]

変更内容を保存し、次の手順に進みます。

## <a name="implement-the-switching-function"></a><a name="vcconswitchingfunctiona4"></a> 切り替え関数を実装する

前の手順では、新しいビューオブジェクトを作成および初期化するコードを追加しました。 最後の主要な部分は、切り替えメソッドを実装することです `SwitchView` 。

アプリケーションクラスの実装ファイル (Mywinapp) の末尾。*CPP*) で、次のメソッド定義を追加します。

[!code-cpp[NVC_MFCDocViewSDI#4](codesnippet/cpp/adding-multiple-views-to-a-single-document_4.cpp)]

変更内容を保存し、次の手順に進みます。

## <a name="add-support-for-switching-the-view"></a><a name="vcconswitchingtheviewa5"></a> ビューを切り替えるためのサポートを追加する

最後の手順では、 `SwitchView` アプリケーションでビューを切り替える必要がある場合に、メソッドを呼び出すコードを追加します。 これを行うには、いくつかの方法があります。ユーザーが新しいメニュー項目を追加して、特定の条件が満たされたときにビューを内部で選択または切り替えることができます。

新しいメニュー項目とコマンドハンドラー関数の追加の詳細については、「 [コマンドとコントロール通知のハンドラー](handlers-for-commands-and-control-notifications.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ドキュメント/ビューアーキテクチャ](document-view-architecture.md)
