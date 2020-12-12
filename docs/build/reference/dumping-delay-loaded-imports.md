---
description: 詳細については、Delay-Loaded インポートのダンプ
title: 遅延読み込みしたインポートのダンプ
ms.date: 11/04/2016
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
ms.openlocfilehash: c57ff6bb4a3dce16b4cb1eb85fdffff4ef272396
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201080"
---
# <a name="dumping-delay-loaded-imports"></a>遅延読み込みしたインポートのダンプ

遅延読み込みされたインポートは、 [dumpbin/imports](imports-dumpbin.md) を使用してダンプし、標準のインポートとは少し異なる情報で表示できます。 これらは、/imports ダンプの独自のセクションに分離され、遅延読み込みのインポートとして明示的にラベル付けされます。 イメージにアンロード情報が含まれている場合は、そのことに注意してください。 バインド情報が存在する場合は、インポートのバインドされたアドレスと共に、ターゲット DLL の日時スタンプが示されます。

## <a name="see-also"></a>関連項目

[リンカーによる Delay-Loaded Dll のサポート](linker-support-for-delay-loaded-dlls.md)
