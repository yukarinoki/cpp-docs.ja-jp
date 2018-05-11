---
title: static ストレージ クラス指定子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a7d61e39eb706721ddf936f88f5df02a6eddf96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="static-storage-class-specifier"></a>static ストレージ クラス指定子
**static** のストレージ クラス指定子により内部レベルで宣言された変数には、グローバル有効期間がありますが、宣言されたブロック内でのみ表示されます。 定数文字列の場合、**static** を使用すると、頻繁に呼び出される関数で頻度の高い初期化のオーバーヘッドを軽減するのに役立ちます。  
  
## <a name="remarks"></a>コメント  
明示的に**静的**変数を初期化しない場合、既定で 0 に初期化されます。 関数内で、**static** はストレージを割り当てますが、定義として動作します。 内部静的変数は、1 つの関数にのみプライベートの永続ストレージ変数を提供します。  
  
## <a name="see-also"></a>参照  
[C ストレージ クラス](c-storage-classes.md)  
[ストレージ クラス (C++)](../cpp/storage-classes-cpp.md)  