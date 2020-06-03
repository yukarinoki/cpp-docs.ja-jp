---
title: 下位互換性
ms.date: 11/04/2016
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
ms.openlocfilehash: 2c2b4570e5e3131911e7f424280f16e9977f047e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438565"
---
# <a name="backward-compatibility"></a>下位互換性

製品バージョン間の互換性を維持するために、ライブラリ OLDNAMES.LIB では古い名前を新しい名前にマップします。 たとえば、`open` は `_open` にマップされます。 OLDNAMES.LIB は、次のコマンドライン オプションの組み合わせを使用してコンパイルする場合にのみ、明示的にリンクする必要があります。

- `/Zl` (オブジェクト ファイルから既定のライブラリ名を省略) と `/Ze` (既定値: Microsoft の拡張機能を使用)

- `/link` (リンカーのコントロール)、`/NOD` (既定のライブラリを検索しない)、`/Ze`

コンパイラのコマンドライン オプションの詳細については、「[コンパイラ リファレンス](../build/reference/compiler-options.md)」をご覧ください。

## <a name="see-also"></a>参照

[互換性](../c-runtime-library/compatibility.md)
