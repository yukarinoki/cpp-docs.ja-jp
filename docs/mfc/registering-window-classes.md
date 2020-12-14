---
description: '詳細情報: ウィンドウクラスの登録'
title: ウィンドウ クラスの登録
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: e31f83b691ad12d845afca6a3a5f18d9ba64b0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218193"
---
# <a name="registering-window-classes"></a>ウィンドウ クラスの登録

Windows 用の従来のプログラミングのウィンドウ "classes" は、任意の数のウィンドウを作成できる "クラス" (C++ クラスではない) の特性を定義します。 この種のクラスは、windows を作成するためのテンプレートまたはモデルです。

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows 用の従来のプログラムでのウィンドウクラスの登録

MFC を使用していない Windows の従来のプログラムでは、"ウィンドウプロシージャ" または "." のウィンドウにすべてのメッセージを処理し `WndProc` ます。は、 `WndProc` "ウィンドウクラスの登録" プロセスを使用して、ウィンドウに関連付けられています。 メインウィンドウは関数に登録され `WinMain` ますが、その他の windows のクラスはアプリケーション内の任意の場所に登録できます。 登録は、関数へのポインターと、 `WndProc` カーソルや背景ブラシなどの仕様を含む構造体に依存します。 構造体は、関数を呼び出す前に、クラスの文字列名と共にパラメーターとして渡され `RegisterClass` ます。 そのため、登録クラスは複数のウィンドウで共有できます。

## <a name="window-class-registration-in-mfc-programs"></a>MFC プログラムでのウィンドウクラスの登録

これに対し、ほとんどのウィンドウクラスの登録アクティビティは、MFC フレームワークプログラムで自動的に実行されます。 MFC を使用している場合は、通常、クラス継承のための通常の C++ 構文を使用して、既存のライブラリクラスから C++ ウィンドウクラスを派生させます。 フレームワークは従来の "登録クラス" を引き続き使用し、いくつかの標準のものを提供し、必要に応じて登録します。 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数を呼び出して、登録されているクラスをのメンバー関数に渡すことで、追加の登録クラスを登録でき `Create` `CWnd` ます。 ここで説明するように、Windows の従来の "登録クラス" は、C++ クラスと混同することはありません。

詳細については、「 [テクニカルノート 1](../mfc/tn001-window-class-registration.md)」を参照してください。

## <a name="see-also"></a>関連項目

[作成 (ウィンドウを)](../mfc/creating-windows.md)
