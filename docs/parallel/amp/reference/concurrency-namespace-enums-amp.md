---
title: 同時実行の名前空間列挙型 (AMP) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58d70b995642eaca3dbefd75383e6d6bf06f2c62
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082438"
---
# <a name="concurrency-namespace-enums-amp"></a>同時実行の名前空間列挙型 (AMP)

|||
|-|-|
|[access_type 列挙型](#access_type)|[queuing_mode 列挙型](#queuing_mode)|

##  <a name="access_type"></a>  access_type 列挙型

データへのさまざまな種類のアクセスを示すために使用される列挙型。

```
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

##  <a name="queuing_mode"></a>  queuing_mode 列挙型

アクセラレータでサポートされているキュー モードを指定します。

```
enum queuing_mode;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`queuing_mode_immediate`|などのことを指定するキュー モード コマンド[parallel_for_each 関数 (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)、呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。|
|`queuing_mode_automatic`|対応するコマンド キューに入れられるコマンドを指定するキュー モード、 [accelerator_view](accelerator-view-class.md)オブジェクト。 コマンドは、デバイスに送信されるときに[accelerator_view::flush](accelerator-view-class.md#flush)が呼び出されます。|

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
