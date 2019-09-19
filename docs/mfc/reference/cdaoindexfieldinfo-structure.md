---
title: CDaoIndexFieldInfo 構造体
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: a8b0ff991b8cc4988192b89d7f70309af9b9112a
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096089"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 構造体

構造`CDaoIndexFieldInfo`体には、データアクセスオブジェクト (DAO) 用に定義されたインデックスフィールドオブジェクトに関する情報が含まれています。

DAO は Office 2013 でサポートされています。 DAO 3.6 は最終バージョンであり、互換性のために残されているものと見なされます。

## <a name="syntax"></a>構文

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>パラメーター

*m_strName*<br/>
インデックスフィールドオブジェクトに一意の名前を付けます。 詳細については、DAO ヘルプの「Name プロパティ」を参照してください。

*m_bDescending*<br/>
Index オブジェクトによって定義されたインデックスの順序を示します。 順序が降順の場合は TRUE。

## <a name="remarks"></a>Remarks

インデックスオブジェクトには、複数のフィールドを含めることができます。これは、テーブル (またはテーブルに基づくレコードセット) がインデックス化されているフィールドを示します。 上のプライマリへの参照は、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)クラス`m_pFieldInfos`の`GetIndexInfo`メンバー関数を呼び出すことによって取得される[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)オブジェクトのメンバーで情報がどのように返されるかを示します。

インデックスオブジェクトとインデックスフィールドオブジェクトは、MFC クラスでは表されません。 代わりに、 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)クラスまたは[CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md)クラスの MFC オブジェクトの基になる DAO オブジェクトには、Indexes コレクションと呼ばれるインデックスオブジェクトのコレクションが含まれています。 各インデックスオブジェクトには、フィールドオブジェクトのコレクションが含まれています。 これらのクラスは、インデックス情報の個々の項目にアクセスするためのメンバー関数を提供します。 `CDaoIndexInfo`また、親オブジェクト`GetIndexInfo`のメンバー関数を呼び出すことによって、オブジェクトを使用して一度にすべてのオブジェクトにアクセスすることもできます。 オブジェクトには、オブジェクトの`CDaoIndexFieldInfo`配列を指すデータ`m_pFieldInfos`メンバーがあります。 `CDaoIndexInfo`

対象となるインデックスオブジェクトが格納されているインデックスのコレクションが格納されているテーブルテーブルまたはレコードセットオブジェクトのメンバー関数を呼び出します。`GetIndexInfo` 次に、 `m_pFieldInfos` [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)オブジェクトのメンバーにアクセスします。 `m_pFieldInfos`配列の長さは、に`m_nFields`格納されます。 `CDaoIndexFieldInfo`は、 `Dump`デバッグビルドでメンバー関数も定義します。 を使用`Dump`すると、 `CDaoIndexFieldInfo`オブジェクトの内容をダンプできます。

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
