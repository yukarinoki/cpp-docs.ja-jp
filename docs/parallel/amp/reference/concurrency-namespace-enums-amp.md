---
title: コンカレンシー名前空間列挙型 (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 2467db27ad36dfcda31dfb5bb45067ada5470d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376316"
---
# <a name="concurrency-namespace-enums-amp"></a>コンカレンシー名前空間列挙型 (AMP)

|||
|-|-|
|[access_type 列挙型](#access_type)|[queuing_mode 列挙型](#queuing_mode)|

## <a name="access_type-enumeration"></a><a name="access_type"></a>access_type列挙

データへのさまざまな種類のアクセスを示すために使用される列挙型。

```cpp
enum access_type;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`access_type_auto`|アクセラレータに最も適した `access_type` を自動的に選択します。|
|`access_type_none`|専用。 割り当ては、アクセラレータ上でのみアクセスでき、CPU 上ではアクセスできません。|
|`access_type_read`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取り可能です。|
|`access_type_read_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では書き込み可能です。|
|`access_type_write`|共有。 割り当ては、アクセラレータ上でアクセスでき、CPU 上では読み取りおよび書き込みの両方ができます。|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a>queuing_mode列挙

アクセラレータでサポートされているキュー モードを指定します。

```cpp
enum queuing_mode;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`queuing_mode_immediate`|parallel_for_each[関数 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)など、すべてのコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されるように指定するキュー イング モード。|
|`queuing_mode_automatic`|[accelerator_view](accelerator-view-class.md)オブジェクトに対応するコマンド・キューにコマンドをキューに入れるように指定するキューイング・モード。 [コマンドは、accelerator_view::flush](accelerator-view-class.md#flush)が呼び出されたときにデバイスに送信されます。|

## <a name="see-also"></a>関連項目

[同時実行名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
