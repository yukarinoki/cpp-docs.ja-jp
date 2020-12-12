---
description: '詳細情報: CWinApp および MFC アプリケーションウィザード'
title: CWinApp および MFC アプリケーション ウィザード
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1ce1f0a84aa5a0f123f9fa8654d1ce286c47d1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309265"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード

スケルトンアプリケーションを作成すると、MFC アプリケーションウィザードによって、 [CWinApp](reference/cwinapp-class.md)から派生したアプリケーションクラスが宣言されます。 MFC アプリケーションウィザードでは、次の項目を含む実装ファイルも生成されます。

- アプリケーションクラスのメッセージマップ。

- 空のクラスコンストラクター。

- クラスの1つだけのオブジェクトを宣言する変数。

- メンバー関数の標準実装 `InitInstance` 。

アプリケーションクラスは、プロジェクトのヘッダーとメインのソースファイルに配置されます。 クラスの名前と作成されたファイルは、MFC アプリケーションウィザードで指定したプロジェクト名に基づいています。 これらのクラスのコードを表示する最も簡単な方法は、 [クラスビュー](/visualstudio/ide/viewing-the-structure-of-code)を使用することです。

提供される標準実装とメッセージマップは、多くの目的に適していますが、必要に応じて変更できます。 これらの実装の中で最も興味深いのは、 `InitInstance` メンバー関数です。 通常は、のスケルトン実装にコードを追加し `InitInstance` ます。

## <a name="see-also"></a>関連項目

[CWinApp: Application クラス](cwinapp-the-application-class.md)<br/>
[オーバーライド可能な CWinApp メンバー関数](overridable-cwinapp-member-functions.md)<br/>
[特別な CWinApp サービス](special-cwinapp-services.md)
