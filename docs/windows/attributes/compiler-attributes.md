---
title: コンパイラ属性 (C++ COM)
ms.date: 10/02/2018
helpviewer_keywords:
- cl.exe compiler, attributes
- attributes [C++/CLI], compiler
ms.assetid: 53cd9bee-1521-48ec-b171-80feac2096cc
ms.openlocfilehash: f8eb15645049085acc047e41d0a4ea769d359871
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168280"
---
# <a name="compiler-attributes"></a>コンパイラ属性

コンパイラ属性は、さまざまな機能を提供します。

|Attribute|説明|
|---------------|-----------------|
|[emitidl](emitidl.md)|すべての後続の IDL 属性を処理し、生成された .idl ファイルに配置するかどうかを決定します。|
|[event_receiver](event-receiver.md)|イベントレシーバーを作成します。|
|[event_source](event-source.md)|イベント ソースを作成します。|
|[export](export.md)|データ構造を .idl ファイルに配置します。|
|[implements](implements-cpp.md)|IDL コクラスのメンバーとして強制されるディスパッチインターフェイスを指定します。|
|[importidl](importidl.md)|生成された .idl ファイルに、指定した .idl ファイルを挿入します。|
|[importlib](importlib.md)|既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。|
|[includelib](includelib-cpp.md)|生成された .idl ファイルに .idl ファイルまたは .h ファイルを含めます。|
|[library_block](library-block.md)|.Idl ファイルのライブラリブロック内にコンストラクトを配置します。|
|[no_injected_text](no-injected-text.md)|属性の使用によってコードが挿入されないようにします。|
|[satype](satype.md)|`SAFEARRAY`のデータ型を指定します。|
|[version](version-cpp.md)|インターフェイスまたはクラスの複数のバージョン間で特定のバージョンを識別します。|

## <a name="see-also"></a>参照

[グループ別の属性](attributes-by-group.md)
