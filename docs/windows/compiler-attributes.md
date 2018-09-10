---
title: コンパイラ属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 1c1ce698992f1f34434a476be83da6f4697f619c
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316537"
---
# <a name="compiler-attributes"></a>コンパイラ属性

コンパイラ属性は、さまざまな機能を提供します。

|属性|説明|
|---------------|-----------------|
|[emitidl](../windows/emitidl.md)|後続のすべての IDL 属性が処理され、生成された .idl ファイル内に配置するかどうかを判断します。|
|[event_receiver](../windows/event-receiver.md)|イベント レシーバーを作成します。|
|[event_source](../windows/event-source.md)|イベント ソースを作成します。|
|[export](../windows/export.md)|.Idl ファイルに配置するデータ構造をによりします。|
|[実装](../windows/implements-cpp.md)|IDL コクラスのメンバーであるが強制されているディスパッチ インターフェイスを指定します。|
|[importidl](../windows/importidl.md)|生成された .idl ファイルには、指定された .idl ファイルを挿入します。|
|[importlib](../windows/importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[includelib](../windows/includelib-cpp.md)|生成された .idl ファイルに含まれる、.idl ファイルまたは .h ファイル。|
|[library_block](../windows/library-block.md)|.Idl ファイルのライブラリ ブロック内で構成要素を配置します。|
|[no_injected_text](../windows/no-injected-text.md)|コンパイラがコードの属性を使用した結果として挿入するを防ぎます。|
|[satype](../windows/satype.md)|データ型を指定します、`SAFEARRAY`します。|
|[version](../windows/version-cpp.md)|インターフェイスまたはクラスの複数のバージョン間で特定のバージョンを識別します。|

## <a name="see-also"></a>関連項目

[グループ別の属性](../windows/attributes-by-group.md)