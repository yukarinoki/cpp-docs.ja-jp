---
title: ATL と MFC の選択に関する推奨事項
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: e4e51f81bbdc54ff09980acfba22037df77abac9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259777"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>ATL と MFC の選択に関する推奨事項

コンポーネントおよびアプリケーションを開発する場合は、2 つの方法のことができます: ATL および MFC (Microsoft Foundation Class ライブラリ)。

## <a name="using-atl"></a>ATL を使用します。

ATL は、C++ では、COM コンポーネントを作成して、小さなフット プリントの管理の両方に高速で簡単な方法です。 ATL を使用すると、すべての MFC を自動的に提供する組み込みの機能を必要としない場合、コントロールを作成します。

## <a name="using-mfc"></a>MFC を使用します。

MFC では、完全なアプリケーション、ActiveX コントロール、およびアクティブなドキュメントを作成できます。 場合、MFC でのコントロールが既に MFC での開発を続行したい場合があります。 新しいコントロールを作成する場合は、すべての MFC の組み込み機能を必要としない場合は、ATL を使用して検討してください。

## <a name="using-atl-in-an-mfc-project"></a>MFC プロジェクトで ATL を使用します。

ウィザードを実行して既存の MFC プロジェクトで ATL を使用するためのサポートを追加することができます。 詳細については、[MFC プロジェクトへの ATL サポートの追加](../mfc/reference/adding-atl-support-to-your-mfc-project.md)を参照してください。

## <a name="see-also"></a>関連項目

[ATL の概要](../atl/introduction-to-atl.md)
