---
title: アプリケーション フレームワーク
ms.date: 11/04/2016
helpviewer_keywords:
- application framework [MFC], building applications
- applications [MFC]
- application framework [MFC]
ms.assetid: 912684e6-4418-49dc-9877-a4cd19d69d20
ms.openlocfilehash: 3d6616380e9461489d208281a34e0b0b4aa2caf0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626015"
---
# <a name="application-framework"></a>アプリケーション フレームワーク

MFC (Microsoft Foundation Class) ライブラリの中核となるのは、C++ 形式の Windows API の大部分をカプセル化することです。 ライブラリクラスは、ウィンドウ、ダイアログボックス、デバイスコンテキスト、一般的な GDI オブジェクト (ブラシ、ペン、コントロール、その他の標準の Windows 項目など) を表します。 これらのクラスは、カプセル化する Windows の構造体に便利な C++ メンバー関数インターフェイスを提供します。 これらのクラスの使用の詳細については、「 [Window オブジェクトのトピック](window-objects.md)」を参照してください。

ただし、MFC ライブラリには、Windows API の C++ カプセル化に基づいて構築された追加のアプリケーション機能のレイヤーも用意されています。 このレイヤーは Windows 用の実用的なアプリケーションフレームワークであり、ツールバー、ステータスバー、印刷、印刷プレビュー、データベースサポート、ActiveX サポートなど、Windows のプログラムに期待される一般的なユーザーインターフェイスのほとんどを提供します。 [クラスを使用して Windows のアプリケーションを記述する](using-the-classes-to-write-applications-for-windows.md)と、フレームワークの詳細が説明されます。

## <a name="see-also"></a>関連項目

[一般的なクラスデザインの考え方](general-class-design-philosophy.md)
