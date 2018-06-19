---
title: ライブラリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d2fb7e69b0557bf96601666c390b3d59412b5a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371165"
---
# <a name="library"></a>LIBRARY
DLL を作成するリンクを示します。 同時には、リンクは、ビルドで .exp ファイルを使用しない場合に、インポート ライブラリを作成します。  
  
```  
LIBRARY [library][BASE=address]  
```  
  
## <a name="remarks"></a>コメント  
 *ライブラリ*引数は、DLL の名前を指定します。 使用することも、 [/out](../../build/reference/out-output-file-name.md)リンカー オプションを DLL の出力名を指定します。  
  
 基本 =*アドレス*引数は、オペレーティング システムは DLL の読み込みに使用するベース アドレスを設定します。 この引数は、0x10000000 の既定の DLL の場所を上書きします。 説明を参照して、 [/base](../../build/reference/base-base-address.md)詳細については、ベース アドレスはオプションです。  
  
 使用してください、 [/DLL](../../build/reference/dll-build-a-dll.md)リンカー オプション、DLL をビルドするときにします。  
  
## <a name="see-also"></a>関連項目  
 [モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)