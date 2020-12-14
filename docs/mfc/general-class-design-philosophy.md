---
description: '詳細情報: 汎用クラスのデザイン思想'
title: 一般的なクラス デザインの考え方
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 96069b5f30cbca8bb310de6b917fd65a280700b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193462"
---
# <a name="general-class-design-philosophy"></a>一般的なクラス デザインの考え方

Microsoft Windows は、C++ 言語が普及する前に設計されています。 何千ものアプリケーションが C 言語の Windows アプリケーションプログラミングインターフェイス (API) を使用しているため、そのインターフェイスは近い将来のために維持されます。 したがって、C++ の Windows インターフェイスはすべて、手続き型の C 言語 API の上に構築する必要があります。 これにより、C++ アプリケーションが C アプリケーションと共存できることが保証されます。

Microsoft Foundation Class ライブラリは、次の設計目標を満たす Windows へのオブジェクト指向のインターフェイスです。

- Windows のアプリケーションを作成する作業が大幅に削減されます。

- C 言語 API の実行速度に相当します。

- 最小限のコードサイズのオーバーヘッド。

- 任意の Windows C 関数を直接呼び出すことができます。

- 既存の C アプリケーションを C++ に簡単に変換できます。

- C 言語の Windows プログラミングエクスペリエンスの既存の基本を活用する機能。

- C++ での Windows API の使用が C よりも簡単になりました。

- ActiveX コントロール、データベースサポート、印刷、ツールバー、ステータスバーなど、複雑な機能の強力な抽象化を使いやすくなりました。

- C++ 言語機能を効果的に使用する、C++ 用の真の Windows API。

MFC ライブラリのデザインの詳細については、以下を参照してください。

- [アプリケーションフレームワーク](application-framework.md)

- [C 言語 API との関係](relationship-to-the-c-language-api.md)

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
