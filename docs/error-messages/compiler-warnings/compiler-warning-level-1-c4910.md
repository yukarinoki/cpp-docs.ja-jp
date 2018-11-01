---
title: コンパイラの警告 (レベル 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: f0d1df0a383b6646d52fc2babc53ca656d49ace6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428198"
---
# <a name="compiler-warning-level-1-c4910"></a>コンパイラの警告 (レベル 1) C4910

'\<識別子 >': '関数' と 'extern' 明示的なインスタンス化の互換性がありません

という名前の明示的なテンプレートをインスタンス化*\<識別子 >* 両方で変更されたが、`__declspec(dllexport)`と`extern`キーワード。 ただし、これらのキーワードは、相互に排他的です。 `__declspec(dllexport)` キーワードは、テンプレート クラスのインスタンス化を意味しますが、 `extern` キーワードは、テンプレート クラスを自動的にインスタンス化しないことを意味します。

## <a name="see-also"></a>関連項目

[明示的なインスタンス化](../../cpp/explicit-instantiation.md)<br/>
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)<br/>
[一般的な規則と制約](../../cpp/general-rules-and-limitations.md)