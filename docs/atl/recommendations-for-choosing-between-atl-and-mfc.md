---
description: '詳細情報: ATL と MFC の選択に関する推奨事項'
title: ATL と MFC の選択に関する推奨事項
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: 506df04ebbd3bc9079e1d40cf14773d9d9a6bd1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159155"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL と MFC の選択に関する推奨事項

コンポーネントとアプリケーションを開発する場合は、ATL と MFC (Microsoft Foundation Class ライブラリ) の2つの方法から選択できます。

## <a name="using-atl"></a>ATL の使用

ATL は、C++ で COM コンポーネントを作成し、小さなフットプリントを維持するための高速で簡単な方法です。 MFC が自動的に提供するすべての組み込み機能を必要としない場合は、ATL を使用してコントロールを作成します。

## <a name="using-mfc"></a>使用 (MFC を)

MFC では、完全なアプリケーション、ActiveX コントロール、およびアクティブなドキュメントを作成できます。 MFC を使用して既にコントロールを作成している場合は、MFC で開発を続行することもできます。 新しいコントロールを作成する場合は、MFC の組み込み機能のすべてが不要な場合は、ATL の使用を検討してください。

## <a name="using-atl-in-an-mfc-project"></a>MFC プロジェクトでの ATL の使用

ウィザードを実行して、既存の MFC プロジェクトで ATL を使用するためのサポートを追加できます。 詳細については、「 [MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ATL の概要](../atl/introduction-to-atl.md)
