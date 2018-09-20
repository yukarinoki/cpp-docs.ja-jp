---
title: MFC のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- customizations, MFC Extensions
ms.assetid: 3b1b7532-8cc9-48dc-9bbe-7fd4060530b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 640d6726623e8fb6d563153823f449f7caefcf30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385002"
---
# <a name="customization-for-mfc"></a>MFC のカスタマイズ

このトピックでは、MFC アプリケーションをカスタマイズするためのヒントを提供します。

## <a name="general-customizations"></a>全般的なカスタマイズ

保存して、レジストリにアプリケーションの状態を読み込むことができます。 このオプションを有効にすると、アプリケーションは、レジストリからの初期状態を読み込みます。 アプリケーションの初期のドッキング レイアウトを変更する場合は、アプリケーションのレジストリ データをクリアする必要があります。 それ以外の場合、レジストリ内のデータを初期レイアウトに加えた変更が上書きされます。

## <a name="class-specific-customizations"></a>クラスに固有のカスタマイズ

追加のカスタマイズのヒントは、次のトピックにあります。

- [CBasePane クラス](../mfc/reference/cbasepane-class.md)

- [CDockablePane クラス](../mfc/reference/cdockablepane-class.md)

- [CDockingManager クラス](../mfc/reference/cdockingmanager-class.md)

- [CMFCBaseTabCtrl クラス](../mfc/reference/cmfcbasetabctrl-class.md)

## <a name="additional-customization-tips"></a>追加のカスタマイズのヒント

[キーボードとマウスのカスタマイズ](../mfc/keyboard-and-mouse-customization.md)

[ユーザー定義のツール](../mfc/user-defined-tools.md)

## <a name="see-also"></a>関連項目

[MFC デスクトップ アプリケーション](../mfc/mfc-desktop-applications.md)<br/>
[カスタマイズによるセキュリティへの影響](../mfc/security-implications-of-customization.md)

