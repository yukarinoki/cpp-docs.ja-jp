---
title: 3.3 タイミング ルーチン
ms.date: 11/04/2016
ms.assetid: 21060d64-cbe8-4e38-8718-3a68d6a57be3
ms.openlocfilehash: 404e9e168c916b70c7cd32042822f290cd560e98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630478"
---
# <a name="33-timing-routines"></a>3.3 タイミング ルーチン

このセクションで説明されている関数は、ポータブルのウォール クロックのタイマーをサポートします。

- `omp_get_wtime`経過したウォール クロック時間を返します。

- `omp_get_wtick`関数は、連続したクロックのティック間 (秒) を返します。