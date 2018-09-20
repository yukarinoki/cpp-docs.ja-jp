---
title: 一般的なクラス デザインの理念 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8fe64ee4d9e6fc678d97c3e9fe37a85e53807541
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416644"
---
# <a name="general-class-design-philosophy"></a>一般的なクラス デザインの考え方

Microsoft Windows は、C++ 言語は有名になるまでに設計されました。 何千ものアプリケーションでは、C 言語の Windows アプリケーション プログラミング インターフェイス (API) を使用するためには当面そのインターフェイスが保持されます。 任意の C++ Windows インターフェイスは、手続き型の C 言語 API 上に構築する必要がありますので。 これは、C++ アプリケーションが C のアプリケーションと共存できることが保証されます。

次の設計目標に合った Windows へのオブジェクト指向インターフェイスを Microsoft Foundation Class ライブラリには。

- Windows のアプリケーションを作成するための労力を大幅に縮小します。

- 実行速度が、C 言語 API と同等です。

- サイズのオーバーヘッドを最小限のコード。

- 任意の Windows C 関数を直接呼び出す機能。

- C++ への既存の C アプリケーションの簡単に変換します。

- C 言語の Windows プログラミングの経験の既存のベースから利用する機能。

- C. でよりも C++ による Windows API を使いやすく

- ActiveX コントロール、データベースのサポート、印刷、ツールバー、およびステータス バーなどの機能を使いやすく強力な抽象化に複雑です。

- C++ 言語の機能を効果的に使用する C++ の Windows API は true。

詳細については、MFC ライブラリの設計を参照してください。

- [アプリケーション フレームワーク](../mfc/application-framework.md)

- [C 言語 API との関係](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

