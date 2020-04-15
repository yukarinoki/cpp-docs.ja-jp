---
title: C 言語 API との関係
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 1fbd4d332f5ade1cb9415448b138ac5bc838307d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372827"
---
# <a name="relationship-to-the-c-language-api"></a>C 言語 API との関係

Windows の他のクラス ライブラリとは別に Mfc (MFC) ライブラリを設定する単一の特性は、C 言語で記述された Windows API に非常に近いマッピングです。 また、通常は、クラス ライブラリへの呼び出しを、Windows API への直接呼び出しと自由に混在させることができます。 ただし、この直接アクセスは、クラスがその API の完全な置き換えであることを意味するものではありません。 開発者は[、SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor)や[GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)などの一部の Windows 関数を直接呼び出す必要があります。 Windows 関数は、明確な利点がある場合にのみ、クラス メンバー関数でラップされます。

ネイティブの Windows 関数呼び出しを行う必要がある場合もあるため、C 言語の Windows API ドキュメントにアクセスする必要があります。 このドキュメントは、Visual C++ に付属しています。

> [!NOTE]
> MFC ライブラリ フレームワークの動作の概要については、「[クラスを使用して Windows 用アプリケーションを記述する](../mfc/using-the-classes-to-write-applications-for-windows.md)」を参照してください。

## <a name="see-also"></a>関連項目

[一般クラスデザイン哲学](../mfc/general-class-design-philosophy.md)
