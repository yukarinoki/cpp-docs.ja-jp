---
title: 一般的なウィンドウ作成順序
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: fb10ced78e230316a6e2982f24c1fb6e2e52ed8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364266"
---
# <a name="general-window-creation-sequence"></a>一般的なウィンドウ作成順序

子ウィンドウなどの独自のウィンドウを作成する場合、フレームワークは[ドキュメント/ビュー作成](../mfc/document-view-creation.md)で説明したものとほぼ同じプロセスを使用します。

MFC で提供されるすべてのウィンドウ クラスは[、2 段階の構築](../mfc/one-stage-and-two-stage-construction-of-objects.md)を採用しています。 つまり、C++ **new**演算子の呼び出し中に、コンストラクターは C++ オブジェクトを割り当てて初期化しますが、対応するウィンドウは作成しません。 これは、ウィンドウ オブジェクトの[Create](../mfc/reference/cwnd-class.md#create)メンバー関数を呼び出すことで、後で行われます。

メンバー`Create`関数は Windows ウィンドウを作成し`HWND`、C++ オブジェクトのパブリック データ メンバー [m_hWnd](../mfc/reference/cwnd-class.md#m_hwnd)に格納します。 `Create`作成パラメータに対して完全な柔軟性を提供します。 を呼`Create`び出す前に、フレームのアイコンとクラス スタイルを設定するために、グローバル関数[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)を使用してウィンドウ クラスを登録する必要があります。

フレーム ウィンドウの場合は、 の代わりに[LoadFrame](../mfc/reference/cframewnd-class.md#loadframe)メンバー関数を`Create`使用できます。 `LoadFrame`を使用すると、ウィンドウの使用するパラメータが少なくなります。 フレームのキャプション、アイコン、アクセラレータ テーブル、メニューなど、リソースから多くの既定値を取得します。

> [!NOTE]
> LoadFrame によって読み込まれるには、アイコン、アクセラレータ テーブル、およびメニュー リソースに**IDR_MAINFRAME**などの共通リソース ID が必要です。

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ウィンドウ オブジェクト](../mfc/window-objects.md)

- [ウィンドウの "クラス" を登録する](../mfc/registering-window-classes.md)

- [ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

- [ドキュメント フレーム ウィンドウの作成](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>関連項目

[ウィンドウの作成](../mfc/creating-windows.md)
