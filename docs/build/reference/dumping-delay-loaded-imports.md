---
title: 遅延読み込みしたインポートのダンプ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13f832f0ea7aaf7b766141ce7df4f83f21e1cdca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372868"
---
# <a name="dumping-delay-loaded-imports"></a>遅延読み込みしたインポートのダンプ
遅延読み込みしたインポートのダンプを使用して[dumpbin/imports](../../build/reference/imports-dumpbin.md)標準インポートよりも少しずつ異なる情報を表示します。 これらは、ダンプ/imports の独自のセクションに分離され、明示的に遅延読み込みしたインポートとしてラベルが付けられます。 イメージに存在する情報をアンロードする場合は、それが表示されます。 バインド情報がある場合は、インポートのバインド アドレスと DLL のターゲットの日付/時刻スタンプが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)