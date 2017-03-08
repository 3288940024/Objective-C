_dataArray = [NSArray array];
        
        //获取系统时间
        NSDateFormatter *dateformatter = [[NSDateFormatter alloc]init];
        [dateformatter setDateFormat:@"yyyyMMddHHmmSS"];
        NSDate *date = [NSDate date];
        NSString *dateString
        = [dateformatter stringFromDate:date];
        
        
        //拼接url
        NSString *urlString = [NSString stringWithFormat:@"https://route.showapi.com/109-35?channelId=%@&channelName=&maxResult=20&needAllList=0&needContent=0&needHtml=0&page=1&showapi_appid=%@&showapi_timestamp=%@&title=&showapi_sign=%@",self.titleStr,appID,dateString,sign];
        
        NSLog(@"wwwww%@",self.titleStr);
        
        
        //构建url
        NSURL *url = [NSURL URLWithString:urlString];
        //根据url创建请求
        NSURLRequest *request = [NSURLRequest requestWithURL:url];
        //创建会话
        NSURLSession *session = [NSURLSession sharedSession];
        NSURLSessionTask *task = [session dataTaskWithRequest:request completionHandler:^(NSData * _Nullable data, NSURLResponse * _Nullable response, NSError * _Nullable error) {
            //返回一个响应
            NSHTTPURLResponse *responce = (NSHTTPURLResponse *)response;
            if (responce.statusCode == 200) {
                id json = [NSJSONSerialization JSONObjectWithData:data options:NSJSONReadingMutableContainers error:nil];
                _dataArray = json[@"showapi_res_body"][@"pagebean"][@"contentlist"];
            }
            dispatch_async(dispatch_get_main_queue(), ^{
                [table reloadData];
            });
        }];
        [task resume];
