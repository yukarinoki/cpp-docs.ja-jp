---
title: MFC のカスタマイズ
ms.date: 11/04/2016
helpviewer_keywords:
- customizations, MFC Extensions
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
ms.openlocfilehash: 3b7597c3709ed700e82af94c78450ee5aff2d99b
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622969"
---
# <a name="customization-for-mfc"></a>MFC のカスタマイズ

このトピックでは、MFC アプリケーションをカスタマイズするためのヒントについて説明します。

## <a name="general-customizations"></a>全般設定

アプリケーションの状態を保存し、レジストリに読み込むことができます。 このオプションを有効にすると、アプリケーションはレジストリから初期状態を読み込みます。 アプリケーションの初期ドッキングレイアウトを変更する場合は、アプリケーションのレジストリデータをクリアする必要があります。 それ以外の場合、レジストリ内のデータは、初期レイアウトに加えられたすべての変更を上書きします。

## <a name="class-specific-customizations"></a>クラス固有のカスタマイズ

その他のカスタマイズのヒントについては、次のトピックを参照してください。

- [CBasePane クラス](reference/cbasepane-class.md)

- [CDockablePane クラス](reference/cdockablepane-class.md)

- [CDockingManager クラス](reference/cdockingmanager-class.md)

- [CMFCBaseTabCtrl クラス](reference/cmfcbasetabctrl-class.md)

## <a name="additional-customization-tips"></a>その他のカスタマイズのヒント

[キーボードとマウスのカスタマイズ](keyboard-and-mouse-customization.md)

[ユーザー定義ツール](user-defined-tools.md)

## <a name="see-also"></a>関連項目

[MFC デスクトップ アプリケーション](mfc-desktop-applications.md)<br/>
[カスタマイズによるセキュリティへの影響](security-implications-of-customization.md)
