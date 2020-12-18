---
description: '詳細情報: naked (C)'
title: naked (C)
ms.date: 11/04/2016
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
ms.openlocfilehash: 8d45371f71ccffda2c7505587f0942671d24b047
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257018"
---
# <a name="naked-c"></a>naked (C)

**Microsoft 固有の仕様**

naked ストレージ クラス属性は C 言語への Microsoft 固有の拡張機能です。 コンパイラは、naked ストレージ クラス属性を指定して宣言されている関数に対しては、プロローグ コードおよびエピローグ コードを含まないコードを生成します。 naked 関数は、インライン アセンブラー コードを使用してプロローグとエピローグのコード シーケンスを独自に作成する必要がある場合に便利です。 naked 関数は、仮想デバイス ドライバーの記述時に特に便利です。

naked 属性の使用に関する具体的情報については、「[naked 関数](../c-language/naked-functions.md)」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)
