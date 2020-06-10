---
title: 一般的なウィンドウ作成順序
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 0b09543d659448454bbc7c2cca6abee5de3013e5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618753"
---
# <a name="general-window-creation-sequence"></a>一般的なウィンドウ作成順序

子ウィンドウなど、独自のウィンドウを作成する場合、フレームワークは[ドキュメント/ビューの作成](document-view-creation.md)で説明されているものとほぼ同じプロセスを使用します。

MFC に用意されているすべてのウィンドウクラスは、 [2 段階の構築](one-stage-and-two-stage-construction-of-objects.md)を採用しています。 つまり、C++ **new**演算子の呼び出し中に、コンストラクターは c++ オブジェクトを割り当てて初期化しますが、対応する Windows ウィンドウは作成しません。 その後、window オブジェクトの[Create](reference/cwnd-class.md#create) member 関数を呼び出します。

この `Create` メンバー関数は、Windows ウィンドウを作成し、そのを `HWND` C++ オブジェクトのパブリックデータメンバー [m_hWnd](reference/cwnd-class.md#m_hwnd)に格納します。 `Create`を使用すると、作成パラメーターよりも柔軟に完全に制御できます。 を呼び出す前に `Create` 、フレームのアイコンとクラスのスタイルを設定するために、ウィンドウクラスをグローバル関数[AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass)に登録することをお勧めします。

フレームウィンドウでは、の代わりに[LoadFrame](reference/cframewnd-class.md#loadframe)メンバー関数を使用でき `Create` ます。 `LoadFrame`Windows ウィンドウでより多くのパラメーターを使用します。 このメソッドは、リソースから多数の既定値を取得します。これには、フレームのキャプション、アイコン、アクセラレータテーブル、メニューなどが含まれます。

> [!NOTE]
> LoadFrame によって読み込まれるためには、アイコン、アクセラレータテーブル、メニューリソースに共通のリソース ID ( **IDR_MAINFRAME**など) が必要です。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウオブジェクト](window-objects.md)

- [ウィンドウ "classes" を登録しています](registering-window-classes.md)

- [破棄 (ウィンドウオブジェクトを)](destroying-window-objects.md)

- [ドキュメント フレーム ウィンドウの作成](creating-document-frame-windows.md)

## <a name="see-also"></a>関連項目

[ウィンドウの作成](creating-windows.md)
