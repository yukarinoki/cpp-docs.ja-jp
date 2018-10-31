---
title: コンパイラ属性 (C++ COM) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9f0483676fd0dd60d893f8931511083d369539dd
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791190"
---
# <a name="compiler-attributes"></a>コンパイラ属性

コンパイラ属性は、さまざまな機能を提供します。

|属性|説明|
|---------------|-----------------|
|[emitidl](emitidl.md)|後続のすべての IDL 属性が処理され、生成された .idl ファイル内に配置するかどうかを判断します。|
|[event_receiver](event-receiver.md)|イベント レシーバーを作成します。|
|[event_source](event-source.md)|イベント ソースを作成します。|
|[export](export.md)|.Idl ファイルに配置するデータ構造をによりします。|
|[実装](implements-cpp.md)|IDL コクラスのメンバーであるが強制されているディスパッチ インターフェイスを指定します。|
|[importidl](importidl.md)|生成された .idl ファイルには、指定された .idl ファイルを挿入します。|
|[importlib](importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[includelib](includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイル。|
|[library_block](library-block.md)|.Idl ファイルのライブラリ ブロック内で構成要素を配置します。|
|[no_injected_text](no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|
|[satype](satype.md)|データ型を指定します、`SAFEARRAY`します。|
|[version](version-cpp.md)|インターフェイスまたはクラスの複数のバージョン間で特定のバージョンを識別します。|

## <a name="see-also"></a>関連項目

[グループ別の属性](attributes-by-group.md)