---
title: 致命的なエラー C1128 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1128
dev_langs:
- C++
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1d2604b17b656efab3a3575469eff6a02df960c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1128"></a>致命的なエラー C1128
セクションの数がオブジェクト ファイル形式の制限を超えています : /bigobj と共にコンパイルしてください  
  
 .obj ファイルが、許容されるセクション数である COFF オブジェクト ファイル形式制限を超えました。  
  
 このセクション制限に到達するを使用した結果を指定できます[/Gy](../../build/reference/gy-enable-function-level-linking.md)とデバッグ ビルドです。**/Gy**により、関数は、独自の COMDAT セクションに移動します。 デバッグ ビルドには、各 COMDAT 関数のデバッグ情報セクションがあります。  
  
 C1128 エラーは、インライン関数が多すぎることが原因で発生することもあります。  
  
 このエラーを解決するには、ソース ファイルを複数のソース コード ファイルに分割、なしでコンパイル **/Gy**、コンパイル時にまたは[/bigobj (増やすセクションの数にします。Obj ファイル)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)です。  せずにコンパイルする場合 **/Gy**、個別に、最適化を指定する必要がありますので **/O2**と **/O1**意味両方 **/Gy**です。  
  
 可能であれば、デバッグ情報なしでコンパイルしてください。  
  
 また、テンプレートの固有のインスタンス化をコンパイラで出力するのではなく、別のソース コード ファイルにこれらを指定する必要もあります。  
  
 コードを移植するときに C1128 可能性があります最初に表示されます、x64 を使用するときにコンパイラ、および後になって x86 コンパイラです。 x64 には、コンパイルされた各関数に関連付けられている少なくとも 4 つのセクションがある **/Gy**テンプレートまたはインライン クラスからインラインまたは: pdata、コードし、ヒント、および可能性のある xdata をデバッグします。  X86 は pdata を持ちません。