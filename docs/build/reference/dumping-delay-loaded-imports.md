---
title: 遅延読み込みしたインポートのダンプ
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: 782da0d29024a8308de0bb4d00656b850629c8ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444162"
---
# <a name="dumping-delay-loaded-imports"></a>遅延読み込みしたインポートのダンプ

遅延読み込みしたインポートのダンプを使用して[dumpbin/imports](../../build/reference/imports-dumpbin.md)標準インポートよりも若干異なる情報を表示します。 ダンプ/imports の独自のセクションに分離され、遅延読み込みしたインポート明示的に付いています。 イメージに含まれている情報をアンロードする場合は、それが表示されます。 バインド情報がある場合、インポートのバインド アドレスと DLL のターゲットの日付/時刻スタンプが表示されます。

## <a name="see-also"></a>関連項目

[リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)