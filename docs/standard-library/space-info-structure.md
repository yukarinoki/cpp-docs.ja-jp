---
title: space_info 構造体
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: b6998f4ac7ced2d85063186edbd47227b6d24ca5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399448"
---
# <a name="spaceinfo-structure"></a>space_info 構造体

ボリュームに関する情報を保持します。

## <a name="syntax"></a>構文

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>メンバー

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|`unsigned long long capacity`|ボリュームを表すことのできるバイト数の合計数を表します。|
|`unsigned long long free`|ボリューム上のデータを表すために使用されないバイト数を表します。|
|`unsigned long long available`|ボリューム上のデータを表すために使用できるバイト数を表します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<filesystem >

**名前空間:** std::experimental::filesystem

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
[ファイル システムのナビゲーション (C++)](../standard-library/file-system-navigation.md)<br/>
