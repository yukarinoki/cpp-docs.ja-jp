---
title: アプリケーション フレームワーク
ms.date: 11/04/2016
helpviewer_keywords:
- application framework [MFC], building applications
- applications [MFC]
- application framework [MFC]
ms.assetid: 912684e6-4418-49dc-9877-a4cd19d69d20
ms.openlocfilehash: b55635de322274ab02372251976d4ebb9511ade5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446517"
---
# <a name="application-framework"></a>アプリケーション フレームワーク

MFC (Microsoft Foundation Class) ライブラリの中核となるのは、Windows API の大部分をフォーム形式でC++カプセル化することです。 ライブラリクラスは、ウィンドウ、ダイアログボックス、デバイスコンテキスト、一般的な GDI オブジェクト (ブラシ、ペン、コントロール、その他の標準の Windows 項目など) を表します。 これらのクラスは、 C++カプセル化する Windows の構造体に便利なメンバー関数インターフェイスを提供します。 これらのクラスの使用の詳細については、「 [Window オブジェクトのトピック](../mfc/window-objects.md)」を参照してください。

ただし、MFC ライブラリには、Windows API のC++カプセル化に基づいて構築された追加のアプリケーション機能のレイヤーも用意されています。 このレイヤーは Windows 用の実用的なアプリケーションフレームワークであり、ツールバー、ステータスバー、印刷、印刷プレビュー、データベースサポート、ActiveX サポートなど、Windows のプログラムに期待される一般的なユーザーインターフェイスのほとんどを提供します。 [クラスを使用して Windows のアプリケーションを記述する](../mfc/using-the-classes-to-write-applications-for-windows.md)と、フレームワークの詳細が説明されます。

## <a name="see-also"></a>参照

[一般的なクラス デザインの考え方](../mfc/general-class-design-philosophy.md)
