---
title: コマンド ライン エラー D8016 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D8016
dev_langs:
- C++
helpviewer_keywords:
- D8016
ms.assetid: eec51312-7471-4f92-94b2-d517cafc8ef5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6ba57b7036aae652b9eb6d885f9105d8bf0826
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607604"
---
# <a name="command-line-error-d8016"></a>コマンド ライン エラー D8016
'オプション 1' と 'option2' コマンド ライン オプションは互換性がありません。  
  
 コマンド ライン オプションを指定することはできません。  
  
 CL などの環境変数、オプションの指定を確認してください。  
  
 **/clr**意味 **/EHa**、その他の操作を指定することはできませんと **/EH**コンパイラ オプションを使用 **/clr**。 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
 Visual C 6.0 プロジェクトを更新後 D8016 が発生する可能性があります。 プロジェクト更新ウィザードの処理を有効にすることがあります **/RTC**オーバーライド プロジェクトのソース コード ファイルごとに、 **/RTC**プロジェクトの設定。  これを解決するには、変更、 **/RTC** 、プロジェクトの設定の既定の設定に、プロジェクト内の各ソース コード ファイルの設定、つまり **/RTC**ファイルごとに有効になります。  
  
 参照してください[/RTC (ランタイム エラー チェック)](../../build/reference/rtc-run-time-error-checks.md)変更する方法について、 **/RTC**プロパティの設定。