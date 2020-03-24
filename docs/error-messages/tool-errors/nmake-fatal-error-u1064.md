---
title: NMAKE の致命的なエラー U1064
ms.date: 11/04/2016
f1_keywords:
- U1064
helpviewer_keywords:
- U1064
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
ms.openlocfilehash: bfc42c458c1932287f17f367d09c4b23c2c201a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80182826"
---
# <a name="nmake-fatal-error-u1064"></a>NMAKE の致命的なエラー U1064

メイクファイルが見つからず、ターゲットが指定されていません

NMAKE コマンドラインで、メイクファイルまたはターゲットが指定されませんでした。現在のディレクトリには、MAKEFILE という名前のファイルが含まれていませんでした。

NMAKE には、メイクファイルまたはコマンドラインターゲット (またはその両方) が必要です。 メイクファイルを NMAKE で使用できるようにするには、/F オプションを指定するか、または MAKEFILE という名前のファイルを現在のディレクトリに配置します。 メイクファイルが指定されていない場合、NMAKE は推論規則を使用してコマンドラインターゲットを作成できます。
