---
title: TEMPLATE_INSTANTIATION_DATA 構造体
description: C++ Build Insights SDK の TEMPLATE_INSTANTIATION_DATA 構造体のリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 15bbb25c3abac339201179e763bffd916dba0480
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040874"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA 構造体

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`TEMPLATE_INSTANTIATION_DATA` 構造体はテンプレートのインスタンス化を表します。

## <a name="syntax"></a>構文

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>メンバー

| 名前 | [説明] |
|--|--|
| `SpecializationSymbolKey` | テンプレート特殊化の種類を表すキー。 この値は分析対象のトレース内で一意です。 |
| `PrimaryTemplateSymbolKey` | 特殊化されたプライマリ テンプレートの種類を表すキー。 この値は分析対象のトレース内で一意です。 |
| `KindCode` | テンプレート インスタンス化の種類。 詳細については、[TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md) に関するページを参照してください。 |

## <a name="remarks"></a>注釈

`TEMPLATE_INSTANTIATION_DATA` 構造体内のキーは分析対象のトレース内で一意です。 ただし、異なるコンパイラ フロントエンド パスから受け取る 2 つの異なるキーで、2 つの同じ型が示されている場合があります。 複数のコンパイラ フロントエンド パスからの `TEMPLATE_INSTANTIATION_DATA` 情報を使用するとき、[SYMBOL_NAME](../event-table.md#symbol-name) イベントを使用し、2 つの型が同じかどうかを判断します。 `SymbolName` イベントは、すべてのテンプレートのインスタンス化が行われた後で、コンパイラ フロントエンド パスの最後に生成されます。

::: moniker-end
