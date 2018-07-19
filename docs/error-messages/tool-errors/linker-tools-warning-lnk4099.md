---
title: リンカー ツールの警告 LNK4099 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4099
dev_langs:
- C++
helpviewer_keywords:
- LNK4099
ms.assetid: 358170a4-07cd-43fe-918f-82c32757ffc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22764705b35b2e882c5a03e819c9812d084dc118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300814"
---
# <a name="linker-tools-warning-lnk4099"></a>リンカー ツールの警告 LNK4099
Pdb ファイル 'filename' が見つかりませんでした 'オブジェクト/ライブラリ' または 'path';オブジェクトをリンク デバッグ情報がありません。  
  
 リンカーは、.pdb ファイルが見つかりませんでした。 格納されているディレクトリにコピー`object/library`です。  
  
 オブジェクト ファイルに関連付けられている .pdb ファイルの名前が見つかりません。  
  
1.  オブジェクト ファイルをライブラリから抽出[lib](../../build/reference/lib-reference.md) **抽出/:**`objectname`**.obj** `xyz` **.lib**です。  
  
2.  .Pdb ファイルへのパスを確認して**dumpbin/section:.debug$ T/rawdata** `objectname` **.obj**です。  
  
 コンパイルすることも[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)pdb を使用する、または削除する必要はありませんので、 [/debug](../../build/reference/debug-generate-debug-info.md)リンカー オプションは、リンク オブジェクトの .pdb ファイルがあるない場合。