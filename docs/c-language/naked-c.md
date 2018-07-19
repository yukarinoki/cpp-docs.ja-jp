---
title: naked (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a60cdec00f3109bfcc332feeaca24ba5d6880f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383119"
---
# <a name="naked-c"></a>naked (C)
**Microsoft 固有の仕様**  
  
 naked ストレージ クラス属性は C 言語への Microsoft 固有の拡張機能です。 コンパイラは、naked ストレージ クラス属性を指定して宣言されている関数に対しては、プロローグ コードおよびエピローグ コードを含まないコードを生成します。 naked 関数は、インライン アセンブラー コードを使用してプロローグとエピローグのコード シーケンスを独自に作成する必要がある場合に便利です。 naked 関数は、仮想デバイス ドライバーの記述時に特に便利です。  
  
 naked 属性の使用に関する具体的情報については、「[naked 関数](../c-language/naked-functions.md)」を参照してください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)