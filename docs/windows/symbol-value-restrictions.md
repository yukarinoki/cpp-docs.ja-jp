---
title: シンボル値の制限 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.value
dev_langs:
- C++
helpviewer_keywords:
- symbols, value restrictions
- restrictions, symbol values
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ed1631d9b8f0c591006c7b708662b3a7321f22b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602745"
---
# <a name="symbol-value-restrictions"></a>シンボル値の制限

シンボル値には、#define プリプロセッサ ディレクティブに対して通常の方法で表現される整数を指定できます。 シンボル値の例をいくつか次に示します。

```
18
4001
0x0012
-3456
```

リソース (アクセラレータ、ビットマップ、カーソル、ダイアログ ボックス、アイコン、メニュー、文字列テーブル、およびバージョン情報) のシンボル値は、0 ～ 32,767 の範囲の 10 進値である必要があります (16 進値は使用できません)。 一部のリソース (ダイアログ ボックスのコントロールや文字列テーブルの個々の文字列など) のシンボル値には、0 ～ 65,534 または、-32,768 ～ 32,767 の範囲の値を使用できます。

リソース シンボルは、16 ビットの値です。 シンボル値は符号付きまたは符号なしとして入力できますが、内部的には符号なし整数として使用されます。 したがって、負の値は対応する正の値にキャストされます。

シンボル値のいくつかの制限を次に示します。

- Visual Studio 開発環境と MFC では、特殊な目的でいくつかの数値の範囲を使用しています。 最上位ビットが設定されたすべての数値 (符号に応じて -32,768 ～ -1 または 32,768 ～ 65,534) は MFC によって予約されています。

- 他のシンボル文字列を使用してシンボル値を定義することはできません。 たとえば、次のシンボル定義はサポートされません。

    ```cpp
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported
    ```

- 引数を持つプリプロセッサ マクロを値の定義として使用することはできません。 例えば:

    ```cpp
    #define   IDD_ABOUT  ID(7) //not supported
    ```

   これは、コンパイル時に `ID` がどのような値に評価されるかに関係なく、有効な式ではありません。

- アプリケーションには、式を使用して定義されたシンボルを含む既存のファイルが存在する可能性があります。 読み取り専用のシンボルとしてシンボルを含める方法の詳細については、次を参照してください。[共有を使用する (読み取り専用) または計算型シンボル](../windows/including-shared-read-only-or-calculated-symbols.md)します。

数値の範囲の詳細については、次を参照してください。 [TN023: 標準 MFC リソース](../mfc/tn023-standard-mfc-resources.md)します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[シンボルの数値の変更](../windows/changing-a-symbol-s-numeric-value.md)  
[シンボル名の制限](../windows/symbol-name-restrictions.md)  
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)