---
title: space_info 構造体 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::tr2::sys::space_info
dev_langs:
- C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b143a37c306320223ac3abe430e41c9750c8ece9
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025784"
---
# <a name="spaceinfo-structure"></a>space_info 構造体

ボリュームに関する情報を保持します。

## <a name="syntax"></a>構文

```cpp
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };
```

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|`unsigned long long available`|ボリューム上のデータを表すために使用できるバイト数を表します。|
|`unsigned long long capacity`|ボリュームを表すことのできるバイト数の合計数を表します。|
|`unsigned long long free`|ボリューム上のデータを表すために使用されないバイト数を表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[space](http://msdn.microsoft.com/7fce0b0e-523b-4598-b218-47245d0204ca)<br/>
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)<br/>
