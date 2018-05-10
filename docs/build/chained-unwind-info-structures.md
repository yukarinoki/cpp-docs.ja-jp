---
title: チェーン アンワインド情報の構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87469a381c038462549d20b105b791ddb17b1656
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="chained-unwind-info-structures"></a>チェーン アンワインド情報の構造
UNW_FLAG_CHAININFO フラグ設定されている場合、アンワインド情報の構造体は、セカンダリのいずれかと共有の例外のハンドラー/チェーン情報アドレス フィールドには、プライマリ アンワインド情報が含まれています。 次のコードを取得しますプライマリ アンワインドについては、あると仮定して`unwindInfo`構造を持つ、UNW_FLAG_CHAININFO フラグが設定されます。  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 チェーン情報は、2 つの状況で役に立ちます。 まず、非連続のコード セグメントを使用できます。 チェーン情報を使用すると、プライマリ アンワインド情報からアンワインド コード配列が重複していないために必要なアンワインド情報のサイズを軽減できます。  
  
 また、揮発性レジスタの保存をグループ化するのにチェーン情報を使用することができます。 関数のエントリのプロローグの外部になるまで、揮発性レジスタの保存、コンパイラが遅れる可能性があります。 グループ化されたコードの前に、関数の部分では、プライマリ アンワインド情報のことでこれを記録して、チェーン チェーンの情報でアンワインド コードが、不揮発性レジスタの保存を反映して、プロローグのサイズが 0 以外の情報を設定します。 その場合は、アンワインド コードは UWOP_SAVE_NONVOL のすべてのインスタンスです。 プッシュを使用した不揮発性レジスタの保存または追加の固定スタック割り当てを使用して、RSP レジスタを変更するグループ化はサポートされていません。  
  
 UNW_FLAG_CHAININFO 設定のある UNWIND_INFO アイテムが UNWIND_INFO 項目にも設定 (複数シュリンク ラップ) UNW_FLAG_CHAININFO RUNTIME_FUNCTION エントリを含めることができます。 最終的に、チェーン アンワインド情報のポインターは、クリア; UNW_FLAG_CHAININFO のある UNWIND_INFO アイテムに到着これは、プライマリの UNWIND_INFO の項目は、実際のプロシージャのエントリ ポイントを指します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)