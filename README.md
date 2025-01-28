import { useState } from 'react';
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import Image from 'next/image';
import { motion } from 'framer-motion';

const Home = () => {
  const [showMore, setShowMore] = useState(false);

  return (
    <div className="bg-gradient-to-r from-yellow-300 to-pink-300 min-h-screen p-4 text-center">
      <header className="text-4xl font-bold text-brown-700 mb-6">Taste the Magic of Popcorn</header>
      <p className="italic text-lg mb-4">"Flavors so good, they'll pop your taste buds!"</p>

      <motion.div
        initial={{ opacity: 0 }}
        animate={{ opacity: 1 }}
        transition={{ duration: 1 }}
        className="grid grid-cols-1 md:grid-cols-2 gap-6"
      >
        <Card className="p-4">
          <Image
            src="/mnt/data/popcorn%20deeped%20in%20chocolate%20and%20splashing%20dripping%20tastefully.jpg"
            alt="Popcorn dipped in chocolate"
            width={500}
            height={500}
            className="rounded-2xl"
          />
          <CardContent>
            <h2 className="text-2xl font-semibold mt-2">Chocolate Bliss</h2>
            <p className="text-sm">Indulge in popcorn coated with the richest chocolate drizzle.</p>
          </CardContent>
        </Card>

        <Card className="p-4">
          <Image
            src="/mnt/data/more%20intimate%20people%20enjoying%20popcorn%20dipped%20in%20caramel.jpg"
            alt="People enjoying caramel popcorn"
            width={500}
            height={500}
            className="rounded-2xl"
          />
          <CardContent>
            <h2 className="text-2xl font-semibold mt-2">Caramel Heaven</h2>
            <p className="text-sm">A buttery caramel dream with every bite.</p>
          </CardContent>
        </Card>
      </motion.div>

      {showMore && (
        <motion.div
          initial={{ y: 50, opacity: 0 }}
          animate={{ y: 0, opacity: 1 }}
          transition={{ duration: 0.5 }}
          className="mt-6"
        >
          <Card className="p-4">
            <Image
              src="/mnt/data/two%20romantic%20people%20enjoying%20popcorn%20.jpg"
              alt="Couple enjoying popcorn"
              width={500}
              height={500}
              className="rounded-2xl"
            />
            <CardContent>
              <h2 className="text-2xl font-semibold mt-2">Romantic Popcorn Moments</h2>
              <p className="text-sm">Sharing love and popcorn under the sunset.</p>
            </CardContent>
          </Card>
        </motion.div>
      )}

      <Button onClick={() => setShowMore(!showMore)} className="mt-4">
        {showMore ? 'Show Less' : 'See More'}
      </Button>
    </div>
  );
};

export default Home;
