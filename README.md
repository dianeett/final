import { Food } from "../../models/Food"; // Assuming you have a Food model

export const resolvers = {
  Query: {
    foods: async () => {
      return await Food.find(); // Query all foods from MongoDB
    }
  },
  Mutation: {
    addFood: async (_, { name, calories }) => {
      const newFood = new Food({ name, calories });
      await newFood.save();
      return newFood;
    }
  }
};
