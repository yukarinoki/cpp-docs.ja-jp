---
title: 下位互換性 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3056b90f3c6f0f62158a9b6dcfe145cda9740c6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092194"
---
# <a name="backward-compatibility"></a>下位互換性

製品バージョン間の互換性を維持するために、ライブラリ OLDNAMES.LIB では古い名前を新しい名前にマップします。 たとえば、`open` は `_open` にマップされます。 OLDNAMES.LIB は、次のコマンドライン オプションの組み合わせを使用してコンパイルする場合にのみ、明示的にリンクする必要があります。

- `/Zl` (オブジェクト ファイルから既定のライブラリ名を省略) と `/Ze` (既定値: Microsoft の拡張機能を使用)

- `/link` (リンカーのコントロール)、`/NOD` (既定のライブラリを検索しない)、`/Ze`

コンパイラのコマンドライン オプションの詳細については、「[コンパイラ リファレンス](../build/reference/compiler-options.md)」をご覧ください。

## <a name="see-also"></a>参照

[互換性](../c-runtime-library/compatibility.md)