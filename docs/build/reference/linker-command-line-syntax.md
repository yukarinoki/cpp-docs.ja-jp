---
title: リンカー コマンドラインの構文 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], syntax
- linker command line [C++]
- LINK tool [C++], command-line syntax
ms.assetid: e2a31e17-77bd-4e74-9305-75b105b26539
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dab367a7bcb03030f807c8f24ecab088308036bd
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42571684"
---
# <a name="linker-command-line-syntax"></a>リンカー コマンド ラインの構文
リンクを実行します。実行可能ファイルを次のコマンド構文を使用します。  
  
```  
LINK arguments  
```  
  
 `arguments`オプションとファイル名を含めるし、任意の順序で指定することができます。 オプションは、処理された最初の場合は、次のファイルです。 引数を区切るためには、1 つ以上のスペースまたはタブを使用します。  
  
> [!NOTE]
>  このツールは、Visual Studio コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 オプションの指定子のコマンドラインでオプションがで構成されています。 ダッシュ (-) またはスラッシュ (/) のいずれかの後に、オプションの名前。 オプション名の省略形は使用できません。 いくつかのオプションは、コロン (:) 後に指定された引数を取る。 スペースまたはタブは許可されませんオプションの指定を除く/COMMENT オプションでは、引用符で囲まれた文字列内にあります。 10 進数または C 言語表記で数値の引数を指定します。 オプション名および関連するキーワードまたはファイル名引数は大文字小文字が区別されませんが、引数としての識別子が大文字小文字を区別します。  
  
 ファイルをリンカーに渡すするには、リンク コマンドの後に、コマンドラインで、ファイル名を指定します。 ファイル名は、絶対または相対パスを指定して、ファイル名にワイルドカードを使用することができます。 ドット (.) とファイル名拡張子を省略すると、リンク ファイルの .obj と見なされます。 リンクやを使用しないファイル名拡張子がないことにファイルの内容に関する判断を行う調べて、ファイルの種類を決定し、それに応じて処理します。  
  
 link.exe は、成功 (エラーなし)、0 を返します。  それ以外の場合、リンカーは、リンクを停止するエラー番号を返します。  たとえば、リンカーは、LNK1104 を生成、リンカーは 1104 を返します。  したがって、エラーが発生、リンカーによって返される最小のエラー番号には 1000 です。  128 の戻り値は、オペレーティング システムまたは .config ファイルのいずれかの構成に問題を表しますlink.exe または c2.dll、ローダーは読み込まれませんでした。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)