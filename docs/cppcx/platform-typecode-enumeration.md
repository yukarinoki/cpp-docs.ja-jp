---
description: '詳細情報: Platform:: の型の列挙'
title: Platform::TypeCode 列挙型
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::TypeCode
helpviewer_keywords:
- Platform::TypeCode Enumeration
ms.assetid: 93c1305f-eb16-4bec-aead-f88d9518b4cf
ms.openlocfilehash: 3e7bc3d5fa3cf8aec29a9aa3f20c7d02489eddf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307887"
---
# <a name="platformtypecode-enumeration"></a>Platform::TypeCode 列挙型

組み込み型を表す数値カテゴリを指定します。

## <a name="syntax"></a>構文

```cpp
enum class TypeCode {};
```

### <a name="members"></a>メンバー

|型コード|説明|
|---------------|-----------------|
|ブール型|Platform::Boolean 型。|
|Char16|default::char16 型。|
|DateTime|DateTime 型です。|
|Decimal|数値型。|
|Double|default::float64 型。|
|Empty|Void|
|Int16|default::int16 型。|
|Int32|default::int32 型。|
|Int64|default::int64 型。|
|Int8|default::int8 型。|
|Object|Platform::Object 型。|
|Single|default::float32 型。|
|String|Platform::String 型。|
|UInt16|default::uint16 型。|
|UInt32|default::uint32 型。|
|UInt64|default::uint64 型。|
|UInt8|default::uint8 型。|

### <a name="requirements"></a>要件

**サポートされている最低限のクライアント:** Windows 8

**サポートされる最小サーバー:** Windows Server 2012

**名前空間:** Platform

**メタデータ:** platform. winmd
