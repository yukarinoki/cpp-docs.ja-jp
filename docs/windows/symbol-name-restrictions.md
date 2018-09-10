---
title: シンボル名の制限 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols [C++], names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 67527717319c4b571ff4b72b83d718c0ac149586
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313326"
---
# <a name="symbol-name-restrictions"></a>シンボル名の制限

シンボル名に関する制限は、次のとおりです。

- すべて[シンボル](../windows/symbols-resource-identifiers.md)アプリケーションのスコープ内で一意である必要があります。 そうすることで、ヘッダー ファイルでのシンボル定義の競合を避けることができます。

- シンボル名で有効な文字は、A ～ Z、a ～ z、0 ～ 9、およびアンダー スコア (_) です。

- シンボル名を数字で始めることはできず、247 文字までに制限されます。

- シンボル名にスペースを使用することはできません。

- シンボル名で大文字と小文字は区別されませんが、最初のシンボル定義での大文字と小文字の区別は維持されます。 シンボルを定義するヘッダー ファイルは、リソース ファイルで定義されているリソースを参照するために、リソース コンパイラ/エディターと C++ プログラムの両方で使用されます。 大文字か小文字かだけが異なる 2 つのシンボル名の場合、C++ プログラムは 2 つの個別のシンボルと見なしますが、リソース コンパイラ/エディターはどちらの名前も 1 つのシンボルを指していると見なします。

   > [!NOTE]
   > 以下に概要が示されている標準シンボル名スキーム (ID*_[キーワード]) に従わず、シンボル名がリソース スクリプト コンパイラで使用されているキーワードと同じである場合、リソース スクリプト ファイルをビルドしようとすると、ランダムであるように見えるエラーが発生し、診断が困難になります。 これを回避するには、標準名前付けスキームに従います。

シンボル名には説明的なプレフィックスがあり、対象となるリソースやオブジェクトの種類を示します。 これらの説明的なプレフィックスは、テキストを組み合わせた ID で始まります。 Microsoft Foundation Class (MFC) ライブラリでは、以下の表に示されているシンボルの名前付け規則が使用されています。

|カテゴリ|プレフィックス|使用|
|--------------|------------|---------|
|リソース|IDR_ IDD_ IDC_ IDI_ IDB_|アクセラレータまたはメニュー (および関連付けられているかカスタムのリソース) ダイアログ ボックス カーソル アイコン ビットマップ|
|メニュー項目|ID_|メニュー項目|
|コマンド|ID_|コマンド|
|コントロールと子ウィンドウ|IDC_|コントロール|
|文字列|IDS_|文字列テーブル内の文字列|
|MFC|AFX_|定義済みの MFC シンボル用に予約されています|

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[シンボルまたはシンボル名 (ID) の変更](../windows/changing-a-symbol-or-symbol-name-id.md)  
[シンボル値の制限](../windows/symbol-value-restrictions.md)  
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)