---
title: CWinApp および MFC アプリケーション ウィザード
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1a46842d7b4d6a588da585d63e2ad56982bb0ff8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447043"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード

スケルトンアプリケーションを作成すると、MFC アプリケーションウィザードによって、 [CWinApp](../mfc/reference/cwinapp-class.md)から派生したアプリケーションクラスが宣言されます。 MFC アプリケーションウィザードでは、次の項目を含む実装ファイルも生成されます。

- アプリケーションクラスのメッセージマップ。

- 空のクラスコンストラクター。

- クラスの1つだけのオブジェクトを宣言する変数。

- `InitInstance` メンバー関数の標準実装。

アプリケーションクラスは、プロジェクトのヘッダーとメインのソースファイルに配置されます。 クラスの名前と作成されたファイルは、MFC アプリケーションウィザードで指定したプロジェクト名に基づいています。 これらのクラスのコードを表示する最も簡単な方法は、[クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)を使用することです。

提供される標準実装とメッセージマップは、多くの目的に適していますが、必要に応じて変更できます。 これらの実装の中で最も興味深いのは、`InitInstance` メンバー関数です。 通常は、`InitInstance`のスケルトン実装にコードを追加します。

## <a name="see-also"></a>参照

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)<br/>
[オーバーライド可能な CWinApp のメンバー関数](../mfc/overridable-cwinapp-member-functions.md)<br/>
[CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)
