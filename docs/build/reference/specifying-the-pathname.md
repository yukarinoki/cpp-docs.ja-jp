---
title: パス名の指定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2dd121909fbe0aa2f9305b7bd5779b995a69719
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-the-pathname"></a>パス名の指定
出力ファイルの各オプションを受け入れる、 *pathname*引数で、場所と、出力ファイルの名前を指定できます。 引数には、ドライブ名、ディレクトリ、およびファイル名を含めることができます。 オプションと引数の間にスペースは使用できません。  
  
 場合*pathname*ファイル名を含む、拡張子のない、コンパイラは、出力、既定の拡張機能です。 場合*pathname*ディレクトリがないファイル名が含まれています、コンパイラは、指定したディレクトリ内の既定の名前を持つファイルを作成します。 既定の名前は、ソース ファイルと出力ファイルの種類に基づいて既定の拡張機能の基本名に基づきます。 のままにする場合*pathname*完全に、コンパイラは既定のディレクトリに既定の名前でファイルを作成します。  
  
 または、 *pathname*引数は、ファイル名ではなくデバイスの名前 (AUX、CON、PRN、または NUL) を指定できます。 デバイス名の一部として、オプションと、デバイス名、またはコロンの間にスペースを使わないでください。  
  
|デバイス名|説明|  
|-----------------|----------------|  
|AUX|補助デバイス|  
|CON|コンソール|  
|PRN|プリンター|  
|NUL|Null デバイス (ファイルを生成しない)|  
  
## <a name="example"></a>例  
 次のコマンドラインは、プリンターにマップ ファイルを送信します。  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## <a name="see-also"></a>関連項目  
 [出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)