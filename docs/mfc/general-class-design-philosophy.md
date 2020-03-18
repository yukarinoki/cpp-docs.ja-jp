---
title: 一般的なクラス デザインの考え方
ms.date: 11/04/2016
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: 34a173802e3fa43615c05da4ce747592f851228f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79441191"
---
# <a name="general-class-design-philosophy"></a>一般的なクラス デザインの考え方

Microsoft Windows は、言語がC++広く普及する前に設計されています。 何千ものアプリケーションが C 言語の Windows アプリケーションプログラミングインターフェイス (API) を使用しているため、そのインターフェイスは近い将来のために維持されます。 したがっC++て、すべての Windows インターフェイスは、手続き型の C 言語 API の上に構築する必要があります。 これによりC++ 、アプリケーションが C アプリケーションと共存できることが保証されます。

Microsoft Foundation Class ライブラリは、次の設計目標を満たす Windows へのオブジェクト指向のインターフェイスです。

- Windows のアプリケーションを作成する作業が大幅に削減されます。

- C 言語 API の実行速度に相当します。

- 最小限のコードサイズのオーバーヘッド。

- 任意の Windows C 関数を直接呼び出すことができます。

- 既存の C アプリケーションをに簡単C++に変換できます。

- C 言語の Windows プログラミングエクスペリエンスの既存の基本を活用する機能。

- を使用した場合よりもC++ 、Windows API を使用した方が簡単になります。

- ActiveX コントロール、データベースサポート、印刷、ツールバー、ステータスバーなど、複雑な機能の強力な抽象化を使いやすくなりました。

- の真のC++ Windows API は、 C++言語機能を効果的に使用します。

MFC ライブラリのデザインの詳細については、以下を参照してください。

- [アプリケーションフレームワーク](../mfc/application-framework.md)

- [C 言語 API との関係](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
