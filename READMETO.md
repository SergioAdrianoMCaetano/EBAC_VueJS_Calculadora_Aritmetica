# E B A C _ V U E j s _ C a l c u l a d o r a - A r i t m � t i c a  
  
 # # #   I n t r o d u � � o  
  
 O   p r o j e t o   e m   q u e s t � o   �   u m a   c a l c u l a d o r a   a r i t m � t i c a   s i m p l e s   d e s e n v o l v i d a   u t i l i z a n d o   V u e . j s ,   u m   f r a m e w o r k   J a v a S c r i p t   p r o g r e s s i v o   p a r a   a   c o n s t r u � � o   d e   i n t e r f a c e s   d e   u s u � r i o .   A   p r o p o s t a   d e s t e   t r a b a l h o   �   c r i a r   u m a   c a l c u l a d o r a   q u e   p e r m i t a   a o s   u s u � r i o s   i n s e r i r   d o i s   n � m e r o s ,   s e l e c i o n a r   u m a   o p e r a � � o   a r i t m � t i c a   ( a d i � � o ,   s u b t r a � � o ,   m u l t i p l i c a � � o   o u   d i v i s � o ) ,   e   o b t e r   o   r e s u l t a d o   i n s t a n t a n e a m e n t e   s e m   a   n e c e s s i d a d e   d e   c l i c a r   e m   u m   b o t � o   p a r a   c a l c u l a r .   E s t e   t i p o   d e   p r o j e t o   �   u m a   e x c e l e n t e   o p o r t u n i d a d e   p a r a   e x p l o r a r   a s   f u n c i o n a l i d a d e s   r e a t i v a s   d o   V u e . j s   e   e n t e n d e r   c o m o   o   f r a m e w o r k   p o d e   f a c i l i t a r   a   c r i a � � o   d e   i n t e r f a c e s   d i n � m i c a s   e   i n t e r a t i v a s .  
  
 # # #   D e s e n v o l v i m e n t o  
  
 P a r a   i m p l e m e n t a r   a   c a l c u l a d o r a   a r i t m � t i c a ,   s e g u i m o s   o s   s e g u i n t e s   p a s s o s :  
  
 1 .   * * E s t r u t u r a   d o   T e m p l a t e   H T M L * * :  
       -   U t i l i z a m o s   o   t e m p l a t e   V u e   p a r a   e s t r u t u r a r   a   i n t e r f a c e   d o   u s u � r i o .   A   c a l c u l a d o r a   i n c l u i   d o i s   c a m p o s   d e   e n t r a d a   p a r a   o s   n � m e r o s ,   u m   s e l e t o r   p a r a   e s c o l h e r   a   o p e r a � � o   a r i t m � t i c a   e   u m a   � r e a   p a r a   e x i b i r   o   r e s u l t a d o .  
       -   O   t e m p l a t e   t a m b � m   i n c l u i   u m   c a b e � a l h o   c o m   o   t � t u l o   d a   a p l i c a � � o   e   u m a   d e s c r i � � o   d i n � m i c a   d o   c � l c u l o   r e a l i z a d o .  
  
         ` ` ` h t m l  
         < t e m p l a t e >  
             < d i v   c l a s s = " c o n t a i n e r " >  
                 < h e a d e r   c l a s s = " p - 5   m b - 4   m t - 4   b g - c a b e c a l h o   r o u n d e d - 3 " >  
                     < h 1 > C a l c u l a d o r a   A r i t m � t i c a < / h 1 >  
                     < p >  
                         O   r e s u l t a d o   d e   { {   e s t a d o . n u m 1   } }   { {   s i m b o l o O p e r a c a o   } }   { {   e s t a d o . n u m 2   } }   f o i   i g u a l   a   { {   r e s u l t a d o   } }  
                     < / p >  
                 < / h e a d e r >  
                 < d i v   c l a s s = " c a l c u l a d o r a " >  
                     < i n p u t   v - m o d e l . n u m b e r = " e s t a d o . n u m 1 "   p l a c e h o l d e r = " P r i m e i r o   n � m e r o "   t y p e = " n u m b e r "   c l a s s = " m - 5 " >  
                     < d i v   c l a s s = " i n p u t - g r o u p " >  
                         < i n p u t   v - m o d e l . n u m b e r = " e s t a d o . n u m 2 "   p l a c e h o l d e r = " S e g u n d o   n � m e r o "   t y p e = " n u m b e r "   c l a s s = " m - 5 " >  
                         < s e l e c t   v - m o d e l = " e s t a d o . o p e r a c a o " >  
                             < o p t i o n   v a l u e = " s o m a r " >   +   < / o p t i o n >  
                             < o p t i o n   v a l u e = " s u b t r a i r " >   -   < / o p t i o n >  
                             < o p t i o n   v a l u e = " m u l t i p l i c a r " >   *   < / o p t i o n >  
                             < o p t i o n   v a l u e = " d i v i d i r " >   /   < / o p t i o n >  
                         < / s e l e c t >  
                     < / d i v >  
                     < p   c l a s s = " r e s u l t a d o   m - 2 " > < s t r o n g > R e s u l t a d o :   < / s t r o n g > { {   r e s u l t a d o   } } < / p >  
                 < / d i v >  
             < / d i v >  
         < / t e m p l a t e >  
         ` ` `  
  
 2 .   * * S c r i p t   V u e * * :  
       -   N o   s c r i p t ,   u t i l i z a m o s   a   A P I   C o m p o s i t i o n   d o   V u e   3   c o m   o   ` s e t u p `   e   o s   h o o k s   r e a t i v o s   ` r e a c t i v e `   e   ` c o m p u t e d ` .  
       -   C r i a m o s   u m   o b j e t o   ` e s t a d o `   u t i l i z a n d o   ` r e a c t i v e `   p a r a   a r m a z e n a r   o s   v a l o r e s   d o s   n � m e r o s   e   a   o p e r a � � o   s e l e c i o n a d a .  
       -   D e s e n v o l v e m o s   u m a   c o m p u t e d   p r o p e r t y   ` s i m b o l o O p e r a c a o `   p a r a   r e t o r n a r   o   s � m b o l o   c o r r e s p o n d e n t e   �   o p e r a � � o   a r i t m � t i c a   e s c o l h i d a .  
       -   O u t r a   c o m p u t e d   p r o p e r t y ,   ` r e s u l t a d o ` ,   �   r e s p o n s � v e l   p o r   c a l c u l a r   o   r e s u l t a d o   c o m   b a s e   n o s   v a l o r e s   i n s e r i d o s   e   n a   o p e r a � � o   s e l e c i o n a d a .  
  
         ` ` ` j a v a s c r i p t  
         < s c r i p t   s e t u p >  
         i m p o r t   {   r e a c t i v e ,   c o m p u t e d   }   f r o m   ' v u e ' ;  
  
         c o n s t   e s t a d o   =   r e a c t i v e ( {  
             n u m 1 :   0 ,  
             n u m 2 :   0 ,  
             o p e r a c a o :   ' s o m a r ' ,  
         } ) ;  
  
         c o n s t   s i m b o l o O p e r a c a o   =   c o m p u t e d ( ( )   = >   {  
             s w i t c h   ( e s t a d o . o p e r a c a o )   {  
                 c a s e   ' s o m a r ' :  
                     r e t u r n   ' + ' ;  
                 c a s e   ' s u b t r a i r ' :  
                     r e t u r n   ' - ' ;  
                 c a s e   ' m u l t i p l i c a r ' :  
                     r e t u r n   ' * ' ;  
                 c a s e   ' d i v i d i r ' :  
                     r e t u r n   ' / ' ;  
                 d e f a u l t :  
                     r e t u r n   ' ' ;  
             }  
         } ) ;  
  
         c o n s t   r e s u l t a d o   =   c o m p u t e d ( ( )   = >   {  
             s w i t c h   ( e s t a d o . o p e r a c a o )   {  
                 c a s e   ' s o m a r ' :  
                     r e t u r n   e s t a d o . n u m 1   +   e s t a d o . n u m 2 ;  
                 c a s e   ' s u b t r a i r ' :  
                     r e t u r n   e s t a d o . n u m 1   -   e s t a d o . n u m 2 ;  
                 c a s e   ' m u l t i p l i c a r ' :  
                     r e t u r n   e s t a d o . n u m 1   *   e s t a d o . n u m 2 ;  
                 c a s e   ' d i v i d i r ' :  
                     r e t u r n   e s t a d o . n u m 2   ! = =   0   ?   e s t a d o . n u m 1   /   e s t a d o . n u m 2   :   ' E r r o :   D i v i s � o   p o r   z e r o ' ;  
                 d e f a u l t :  
                     r e t u r n   0 ;  
             }  
         } ) ;  
         < / s c r i p t >  
         ` ` `  
  
 3 .   * * E s t i l o s   C S S * * :  
       -   A d i c i o n a m o s   e s t i l o s   C S S   p a r a   m e l h o r a r   a   a p r e s e n t a � � o   d a   c a l c u l a d o r a .   U t i l i z a m o s   c l a s s e s   C S S   p a r a   d e f i n i r   o   l a y o u t   d o s   e l e m e n t o s ,   c o m o   c a b e � a l h o ,   c a m p o s   d e   e n t r a d a   e   s e l e t o r .  
  
         ` ` ` c s s  
         < s t y l e   s c o p e d >  
         b o d y   {  
             b a c k g r o u n d - c o l o r :   # f 0 f 0 f 0 ;   / *   C o r   d e   f u n d o   d e s e j a d a   * /  
         }  
  
         . b g - c a b e c a l h o   {  
             b a c k g r o u n d - c o l o r :   # 1 8 5 A B D ;  
             c o l o r :   # f f f ;  
         }  
  
         . c a l c u l a d o r a   {  
             d i s p l a y :   f l e x ;  
             f l e x - d i r e c t i o n :   c o l u m n ;  
             t e x t - a l i g n :   l e f t ;  
             a l i g n - i t e m s :   c e n t e r ;  
         }  
  
         . i n p u t - g r o u p   {  
             d i s p l a y :   f l e x ;  
             a l i g n - i t e m s :   c e n t e r ;  
         }  
  
         i n p u t ,   s e l e c t   {  
             m a r g i n :   1 0 p x   0 ;  
             p a d d i n g :   1 0 p x ;  
             f o n t - s i z e :   1 6 p x ;  
         }  
  
         . r e s u l t a d o   {  
             f o n t - s i z e :   2 0 p x ;  
             f o n t - w e i g h t :   b o l d ;  
         }  
         < / s t y l e >  
         ` ` `  
  
 # # #   C o n c l u s � o  
  
 A   c o n s t r u � � o   d e s t a   c a l c u l a d o r a   a r i t m � t i c a   u t i l i z a n d o   V u e . j s   d e m o n s t r a   a   e f i c � c i a   d o   f r a m e w o r k   e m   c r i a r   i n t e r f a c e s   d i n � m i c a s   e   r e a t i v a s .   A t r a v � s   d o   u s o   d a s   A P I s   r e a t i v a s   d o   V u e ,   c o n s e g u i m o s   d e s e n v o l v e r   u m a   a p l i c a � � o   q u e   r e s p o n d e   i n s t a n t a n e a m e n t e   � s   m u d a n � a s   n o s   i n p u t s   d o s   u s u � r i o s ,   o f e r e c e n d o   u m a   e x p e r i � n c i a   i n t e r a t i v a   e   a m i g � v e l .   E s t e   p r o j e t o   n � o   s �   a t e n d e   a o s   r e q u i s i t o s   p r o p o s t o s ,   m a s   t a m b � m   s e r v e   c o m o   u m   e x e m p l o   p r � t i c o   d e   c o m o   a p l i c a r   V u e . j s   e m   c e n � r i o s   r e a i s ,   f a c i l i t a n d o   o   a p r e n d i z a d o   e   a   a p l i c a � � o   d e   c o n c e i t o s   f u n d a m e n t a i s   d e   d e s e n v o l v i m e n t o   f r o n t e n d . 