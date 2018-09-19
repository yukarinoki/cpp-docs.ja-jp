---
title: チェーン アンワインド情報の構造 |Microsoft Docs
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
ms.openlocfilehash: 6da09387595188026d855fb99a49b588e6f21aa3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715027"
---
# <a name="chained-unwind-info-structures"></a>チェーン アンワインド情報の構造

UNW_FLAG_CHAININFO フラグが設定されている場合、そのアンワインド情報構造体には、セカンダリの 1 つと、共有の例外のハンドラー/チェーン情報アドレス フィールドには、プライマリのアンワインド情報が含まれています。 次のコードを取得しますプライマリ アンワインドについては、あると仮定して`unwindInfo`構造を持つ、UNW_FLAG_CHAININFO フラグが設定されます。

```
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);
```

チェーン情報は、2 つの状況で役に立ちます。 まず、非連続のコード セグメントを使用できます。 チェーン情報を使用するには、プライマリ アンワインド情報からアンワインド コード配列を複製する必要はありませんので、必要なアンワインド情報のサイズを小さくことができます。

Volatile レジスタの保存をグループ化するのにチェーン情報を使用することもできます。 関数のエントリのプロローグの外になるまで、揮発性レジスタの保存、コンパイラが遅れる可能性があります。 グループ化されたコードの前に、関数の部分の情報をプライマリ アンワインドすることでこれを記録して、チェーンのプロローグのアンワインド コードが、不揮発性レジスタの保存を反映ゼロでないサイズの情報を設定します。 その場合は、アンワインド コードは、UWOP_SAVE_NONVOL のすべてのインスタンスです。 PUSH を使用して不揮発性レジスタを保存します。 または、追加の固定スタック割り当てを使用して、RSP レジスタを変更するグループ化がサポートされていません。

UNW_FLAG_CHAININFO 設定のある UNWIND_INFO アイテムは、ある UNWIND_INFO アイテムにも UNW_FLAG_CHAININFO 設定 (複数シュリンク) がある RUNTIME_FUNCTION エントリを含めることができます。 最終的には、チェーン アンワインド情報ポインターは、クリア; UNW_FLAG_CHAININFO のある UNWIND_INFO アイテムに到着します。これは、プライマリの UNWIND_INFO の項目は、実際の手順のエントリ ポイントを指します。

## <a name="see-also"></a>関連項目

[例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)