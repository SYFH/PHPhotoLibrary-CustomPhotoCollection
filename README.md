## 简介

该分类用于保存图像到自定义相册

## 包含的方法

```
/**
 *  保存照片到自定义相册或相机胶卷
 *  
 *       |image| : 图片, 不能为空
 *   |albumName| : 自定义相册的名字, 如果没有同名的相册, 将会创建一个新的相册, 内容为空时为保存到相机胶卷
 *  |completion| : 当保存图片到自定义相册成功时的回调, 返回一个BOOL值
 *     |failure| : 当保存图片到自定义相册失败时的回调, 返回一个自定义错误, 以判断是哪一处出错
 */
- (void)saveImage:(UIImage * _Nullable)image
          toAlbum:(NSString * _Nullable)albumName
       completion:(void(^ _Nullable)(BOOL success))completion
          failure:(void(^ _Nullable)(NSError * _Nullable error))failure;
```

## 如何使用

```
[[PHPhotoLibrary sharedPhotoLibrary] saveImage:[UIImage imageNamed:@"test"]
                                       toAlbum:@"CutomPhoneCollection"
                                    completion:^(BOOL success) {
                                    
                                               //保存成功
                                               
                                     } failure:^(NSError * _Nullable error) {
                                     
                                               //保存失败
                                               
                                     }];
```

## 适用范围

1. 系统: `iOS 8.x`及以上可以使用, `iOS 7.x` 及以下不能使用
2. 目前还未测试使用在Swift中的状态

## 注意事项

1. 保存方法执行线程默认为`子线程`, 如果需要在回调里执行UI操作, 请在主线程中操作.
2. 待定...
